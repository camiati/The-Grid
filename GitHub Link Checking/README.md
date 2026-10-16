# GitHub Link Checking

A GitHub Actions workflow that checks every external link in a repo's Markdown files on a schedule, opens an issue when links break, and blocks pull requests that add broken links. This repo runs it.

*Links verified October 2026.*

## How it works

| Trigger | What happens |
|---|---|
| Monthly&nbsp;schedule | Checks all links; opens an issue listing any failures |
| Manual&nbsp;run | Same as scheduled, from the "Run workflow" button in the Actions tab |
| Pull&nbsp;request | Checks all links; fails the check if any are broken, blocking the merge |

## Setup

Create `.github/workflows/link-check.yml`:

```yaml
name: Check links

on:
  schedule:
    - cron: "0 13 1 * *"   # 1st of every month, 13:00 UTC
  workflow_dispatch:         # adds a "Run workflow" button in the Actions tab
  pull_request:              # runs on every pull request, as a required check

permissions:
  contents: read
  issues: write

jobs:
  check-links:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v5

      - name: Check links
        id: lychee
        uses: lycheeverse/lychee-action@v2
        with:
          fail: false
          args: >-
            --no-progress
            --scheme https --scheme http
            --accept '200..=299,403,429'
            --max-concurrency 4
            --max-retries 2
            --exclude 'acq\.osd\.mil'
            './**/*.md'

      - name: Open an issue if links are broken (scheduled and manual runs)
        if: steps.lychee.outputs.exit_code != 0 && github.event_name != 'pull_request'
        env:
          GH_TOKEN: ${{ github.token }}
        run: gh issue create --title "Broken links found $(date +%Y-%m-%d)" --body-file ./lychee/out.md

      - name: Fail the check if links are broken (pull requests)
        if: steps.lychee.outputs.exit_code != 0 && github.event_name == 'pull_request'
        run: |
          echo "Broken links found. See the job summary for details."
          exit 1
```

## Settings explained

| Setting | Why |
|---|---|
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

**It's free for public repos.** Standard GitHub-hosted runners cost nothing in public repositories.

**It sends real requests.** Every run visits every linked site. Keep concurrency low, and get sign-off if the links point at systems you don't own.

**Expect false positives.** Government sites often block cloud servers or use certificates the runner doesn't trust. Exclude those domains and check them manually.

**Treat failures like findings.** Identify the root cause, fix it, re-run to verify, and document the resolution before closing. [Issue #1](https://github.com/camiati/The-Grid/issues/1) in this repo is a worked example.

**Scheduled runs pause after 60 days of inactivity.** GitHub disables schedules in public repos with no recent commits. It emails you first, and re-enabling takes one click.

**Watch the repo for issues.** Bot-opened issues don't notify you automatically. Use **Watch → Custom → Issues**.

**Control mapping:** continuous monitoring of published content (SOC 2 CC4.1, monitoring activities).
