# GitHub Supply Chain Hardening

Controls that protect a repo from compromised third-party actions and leaked credentials:
- pinning actions to exact commits, enforcing that pinning, delaying new releases, and scanning for secrets. This repo runs all of them.

*Last reviewed October 2026.*

## Controls

| Control | Where | What it does |
|---|---|---|
| Pin&nbsp;actions&nbsp;to&nbsp;SHAs | Workflow files | Runs one exact, unchangeable version of each action |
| Require&nbsp;pinning | Settings → Actions → General | Blocks any workflow that references an action by tag |
| Dependabot&nbsp;cooldown | `.github/dependabot.yml` | Waits 7 days after a release before proposing it |
| Dependabot&nbsp;alerts | Settings → Advanced Security | Flags dependencies with known vulnerabilities |
| Secret&nbsp;scanning | Settings → Advanced Security | Detects credentials committed to the repo |
| Push&nbsp;protection | Settings → Advanced Security | Blocks a commit containing a credential before it lands |

## Pinning an action

1. Open the action's official releases page, for example `github.com/actions/checkout/releases`.
2. Find the release marked **Latest** and click its commit ID.
3. Copy the full 40-character SHA.
4. Reference it with the version in a comment:

```yaml
uses: actions/checkout@3d3c42e5aac5ba805825da76410c181273ba90b1 # v7.0.1
```

Dependabot updates both the SHA and the comment when a new version is released.

## Primary sources

| Resource | Purpose |
|---|---|
| [Security&nbsp;hardening&nbsp;for&nbsp;Actions](https://docs.github.com/en/actions/security-for-github-actions/security-guides/security-hardening-for-github-actions#using-third-party-actions) | GitHub's guidance on using third-party actions |
| [Keeping&nbsp;actions&nbsp;up&nbsp;to&nbsp;date](https://docs.github.com/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/keeping-your-actions-up-to-date-with-dependabot) | Dependabot configuration for actions |

## Practitioner notes

**Tags can move; SHAs can't.**
- An action's owner, or an attacker who compromises the owner, can point a tag like `@v7` at different code.
- In the March 2025 tj-actions/changed-files compromise, attackers did exactly that, and every workflow using the tag ran the malicious version.

**Get SHAs from the official repo.**
- Commits from a fork can be referenced through the original repo's name, so a SHA alone doesn't prove it belongs to the official project.
- Copy it from the official release page.

**Always add the version comment.**
- A bare SHA tells a reader nothing, and Dependabot relies on the comment to keep the version label accurate.

**Enforce, don't just practice.**
- The require-pinning setting turns a habit into a control.
- Enable it after every workflow is pinned, or unpinned workflows will stop running.

**A cooldown trades speed for safety.**
- Most compromised releases are detected and pulled within days.
- Waiting a week avoids adopting one, at the cost of slower updates.
- Security fixes for known vulnerabilities still come through Dependabot alerts.

**Grant workflows the minimum permissions.**
- A `permissions:` block limits what the workflow's token can do if something goes wrong.
- This repo's link checker can read code and open issues, nothing else.

**Push protection is on by default for public repos.**
- Check that it's enabled anyway, and treat a blocked push as a finding: rotate the credential, even if it never landed.

**Control mapping:**
- third-party and supplier risk (SOC 2 CC9.2; NIST SP 800-171 Rev. 3 supply chain risk management, 03.17) and protection of credentials (SOC 2 CC6.1).
