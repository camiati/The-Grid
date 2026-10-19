# GitHub Dependabot

GitHub's built-in tool for keeping dependencies current. 
Here it watches the actions used in this repo's workflows and opens a pull request when a new version is released. 
Those pull requests go through branch protection and the required checks like any other change.

*Links verified October 2026.*

## How it works

| Step | What happens |
|---|---|
| Monthly&nbsp;check | Dependabot compares each action in `.github/workflows/` to its latest release |
| Update&nbsp;found | Dependabot opens one pull request with all action updates grouped together |
| Review | The pull request runs the required checks; you review the release notes and merge |

## Setup

The configuration is in this repo at [`.github/dependabot.yml`](../.github/dependabot.yml), with comments explaining each setting. 
No other setup is needed; Dependabot reads the file once it's on the default branch.

## Settings explained

| Setting | Why |
|---|---|
| `package-ecosystem: "github-actions"` | Watches actions referenced in workflow files |
| `directory: "/"` | Required for actions; covers workflows in `.github/workflows` |
| `interval: "monthly"` | Matches the repo's other monthly automation |
| `groups` | Bundles all action updates into a single pull request instead of one per action |
| `commit-message: prefix` | Makes Dependabot's commits easy to spot in history |
| `cooldown: default-days: 7` | Waits a week after a release before proposing it, avoiding freshly compromised releases |

## Primary sources

| Resource | Purpose |
|---|---|
| [Keeping&nbsp;actions&nbsp;up&nbsp;to&nbsp;date](https://docs.github.com/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/keeping-your-actions-up-to-date-with-dependabot) | GitHub's documentation for Dependabot with actions |

## Practitioner notes

**Pinned SHAs keep Dependabot active.**
- Actions referenced by a major tag like `@v2` float silently to new minor releases, so Dependabot only proposes major versions.
- This repo pins actions to exact commit SHAs, so Dependabot proposes every update for review. See the Supply Chain Hardening page.

**Read the release notes before merging.**
- A major version can change behavior.
- Dependabot links the release notes in the pull request.

**Required checks still apply.** 
- Dependabot can't bypass branch protection.
- Its pull requests wait for the same checks as yours.

**Version updates and security alerts are separate.**
- This file handles routine version updates.
- Dependabot alerts, which flag known vulnerabilities, are turned on separately in the repo's security settings.

**Control mapping:** 
- vulnerability and patch management for third-party components (SOC 2 CC7.1; NIST SP 800-171 3.14.1, identifying and correcting flaws in a timely manner).
