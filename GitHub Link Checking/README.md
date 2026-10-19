# GitHub Link Checking

A GitHub Actions workflow that checks external links in a repo's Markdown files. It runs a full check monthly and opens an issue when links break, and it checks only the changed files on pull requests, blocking merges that add broken links. This repo runs it.

*Links verified October 2026.*

## How it works

| Trigger | What it checks | On failure |
|---|---|---|
| Monthly&nbsp;schedule | Every link in every Markdown file | Opens an issue |
| Manual&nbsp;run | Every link in every Markdown file | Opens an issue |
| Pull&nbsp;request | Only links in Markdown files the pull request changed | Fails the check, blocking the merge |

A pull request that changes no Markdown files passes without checking anything.

## Setup

The full workflow, with comments explaining each step, is in this repo at [`.github/workflows/link-check.yml`](../.github/workflows/link-check.yml). Copy it into the same path in your own repo.

## Settings explained

| Setting | Why |
|---|---|
| `fetch-depth: 0` | Fetches full history so a pull request can be compared to main |
| `git diff ... -- '*.md'` | Lists the Markdown files a pull request changed, using Git itself and no extra actions |
| `--scheme https --scheme http` | Checks web links only. GitHub handles links between files in the repo |
| `--accept '200..=299,403,429'` | Treats blocked (403) and rate-limited (429) responses as passing, to avoid false alarms from sites that block cloud servers |
| `--max-concurrency 4` | Keeps request volume polite |
| `--exclude 'acq\.osd\.mil'` | Skips a domain whose certificate the GitHub runner doesn't trust. Adjust for your own false positives |
| `issues: write` | Lets the workflow open issues |

## Primary sources

| Resource | Purpose |
|---|---|
| [lychee&#8209;action](https://github.com/lycheeverse/lychee-action) | The link checker action and its options |
| [GitHub&nbsp;Actions&nbsp;billing](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions) | Confirms standard runners are free for public repos |

## Practitioner notes

**Check what changed, not everything.** 
- Re-checking every link on every pull request multiplies traffic to the linked sites and lets an unrelated broken link block your edit.
- Full checks belong on the schedule.

**Prefer built-in tools over extra actions.**
- Listing changed files with `git diff` avoids adding a third-party action.
- A popular changed-files action was compromised in a 2025 supply-chain attack.

**Validate anything a pull request controls.**
- File names come from whoever opened the pull request.
- The workflow allows only simple file names before passing them to the link checker.

**It's free for public repos.**
- Standard GitHub-hosted runners cost nothing in public repositories.

**It sends real requests.**
- Every run visits every link it checks.
- Keep concurrency low, and get sign-off if the links point at systems you don't own.

**Expect false positives.**
- Government sites often block cloud servers or use certificates the runner doesn't trust.
- Exclude those domains and check them manually.

**Treat failures like findings.**
- Identify the root cause, fix it, re-run to verify, and document the resolution before closing.
- [Issue #1](https://github.com/camiati/The-Grid/issues/1) in this repo is a worked example.

**Scheduled runs pause after 60 days of inactivity.**
- GitHub disables schedules in public repos with no recent commits.
- It emails you first, and re-enabling takes one click.

**Watch the repo for issues.** 
- Bot-opened issues don't notify you automatically.
- Use **Watch → Custom → Issues**.

**Control mapping:** 
- Continuous monitoring of published content (SOC 2 CC4.1, monitoring activities).
