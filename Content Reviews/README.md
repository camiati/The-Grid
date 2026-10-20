# Content Reviews

A quarterly review of every page in The Grid against current primary sources. The link checker confirms links still load; content reviews confirm what the pages say is still true.

*Last reviewed October 2026.*

## Process

| Step | What happens |
|---|---|
| 1.&nbsp;Snapshot | Download the repo as a ZIP from the main branch |
| 2.&nbsp;Review | Check every time-sensitive claim against current primary sources, and check internal links between pages |
| 3.&nbsp;Report | Write findings to `Content Reviews/YYYY-MM-DD.md`: structural fixes, content updates, and what was verified as still accurate |
| 4.&nbsp;Fix | Apply fixes through a pull request that includes the report, so findings and fixes are reviewed together |
| 5.&nbsp;Date | Update the "Last reviewed" line on every page reviewed |

## Schedule

Quarterly, or sooner when a tracked development lands. Current triggers:

| Trigger | Affects |
|---|---|
| CMMC Reform Task Force report published | CMMC, DFARS |
| FAR CUI final rule published | CUI Program, NIST SP 800-171 |
| FOCI final rule for unclassified contracts published | DFARS, NISPOM |
| DoD guidance on FedRAMP 20x | FedRAMP 20x, FedRAMP Rev 5, DFARS |

## Reviews

| Date | Findings |
|---|---|
| [October&nbsp;19,&nbsp;2026](./2026-10-19.md) | 2 broken internal links, 11 missing review dates, 3 pages with outdated content |

## Practitioner notes

**Working links aren't current content.** 
- Every link on the CMMC page passed while the page still missed the Phase 2 suspension.
- Automated link checks and human content reviews catch different failures.

**Keep the report with the fixes.** 
- Committing the review report in the same pull request as the fixes leaves an audit trail: what was found, what changed, and who approved it.

**Review the diff, not just the check.**
- In the first review, the link checker passed on a pull request that still contained a broken internal link and a formatting error.
- Both were caught by reading the Files changed tab.

**Control mapping:** 
- periodic review of published guidance (SOC 2 CC2.1, quality of information; CC4.1, monitoring activities).