# GitHub Branch Protection

A GitHub ruleset that stops direct commits to the main branch. Every change goes through a pull request and must pass automated checks before it merges. This repo runs it.

*Last reviewed October 2026.*

## Rules

| Rule | Why |
|---|---|
| Require&nbsp;a&nbsp;pull&nbsp;request | Every change is proposed, visible, and recorded before it lands |
| Require&nbsp;status&nbsp;checks | Automated tests, here the link checker, must pass before merging |
| Block&nbsp;force&nbsp;pushes | History can't be rewritten |
| Restrict&nbsp;deletions | The main branch can't be deleted |
| Empty&nbsp;bypass&nbsp;list | The rules apply to administrators too |

## Setup

1. **Settings** → **Rules** → **Rulesets** → **New ruleset** → **New branch ruleset**.
2. Name it, set **Enforcement status** to **Active**, and leave the bypass list empty.
3. **Target branches** → **Add target** → **Include default branch**.
4. Keep **Restrict deletions** and **Block force pushes** checked.
5. Check **Require a pull request before merging**. On a solo repo, set required approvals to 0.
6. Check **Require status checks to pass** → **Add checks** → select your check (for example, `check-links`).
7. Click **Create**.

## Primary sources

| Resource | Purpose |
|---|---|
| [About&nbsp;rulesets](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets) | GitHub's documentation, including plan availability |

## Practitioner notes

**Free on public repos.**
- Rulesets are available on public repositories with GitHub Free.

**Solo repos need 0 approvals.**
- GitHub won't let you approve your own pull request, so requiring 1 locks you out.
- In a team, require at least one approval from someone other than the author.

**Required checks must run on pull requests.**
- A workflow that only runs on a schedule never reports on a pull request, so the merge waits forever. Add a `pull_request` trigger.

**Avoid path filters on required checks.**
- If the workflow only runs when certain files change, pull requests that don't touch those files will never get the check and can't merge.

**A check appears in the picker only after it has run.**
- Run the workflow once before adding it to the ruleset.

**Control mapping:**
- change management (SOC 2 CC8.1; NIST SP 800-171 3.4.3, tracking, reviewing, and approving changes).
- A solo repo shows the process but not separation of duties; a team setup adds required reviewers.
