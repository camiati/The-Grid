# DFARS Cybersecurity Clauses

Defense Federal Acquisition Regulation Supplement (DFARS)
- clauses that put cybersecurity requirements into DoD contracts
- 252.204-7012 is the foundation; the others add assessment, reporting, certification, and cloud requirements on top of it.

*Last reviewed October 2026.*

## The clauses

| Clause | What it requires |
|---|---|
| [252.204‑7012](https://www.acquisition.gov/dfars/252.204-7012-safeguarding-covered-defense-information-and-cyber-incident-reporting.) | Implement NIST SP 800-171 on systems with covered defense information, report cyber incidents within 72 hours, preserve evidence, meet cloud requirements, flow down to subs. Unchanged. |
| [252.204‑7021](https://www.acquisition.gov/dfars/252.204-7021-contractor-compliance-cybersecurity-maturity-model-certification-level-requirements.) | Maintain the CMMC status required by the contract, affirm continuing compliance, flow down to subs. Unchanged, but Phase 2 third-party requirements are suspended. |
| [252.240‑7997](https://www.acquisition.gov/sites/default/files/page_file_uploads/DoD_RFO_Deviation_Part-40.pdf) | Formerly 252.204-7020. Gives DoD access for government-run Medium and High assessments and flows down to subs. The Basic self-assessment language was removed. |
| [252.204‑7019](https://www.ecfr.gov/current/title-48/chapter-2/subchapter-H/part-252/subpart-252.2/section-252.204-7019) | No longer included in new solicitations as of February 1, 2026. Older contracts may still carry it. |
| [252.239‑7010](https://www.acquisition.gov/dfars/252.239-7010-cloud-computing-services.) | Applies when you provide cloud services to DoD, not when you use cloud internally |

### Policy and guidance

| Resource | Purpose |
|---|---|
| [DFARS Subpart 204.73](https://www.acquisition.gov/dfars/subpart-204.73-safeguarding-covered-defense-information-and-cyber-incident-reporting) | Policy behind 7012, 7019, and 7020 |
| [DFARS Subpart 204.75](https://www.acquisition.gov/dfars/subpart-204.75-cybersecurity-maturity-model-certification) | Policy behind 7021 and CMMC |
| [Class&nbsp;Deviation&nbsp;2026&#8209;O0025](https://www.acquisition.gov/sites/default/files/page_file_uploads/DoD_RFO_Deviation_Part-40.pdf) | The February 2026 Revolutionary FAR Overhaul deviation that created DFARS Part 240 |
| [NIST&nbsp;SP&nbsp;800&#8209;171&nbsp;DoD&nbsp;Assessment&nbsp;Methodology](https://www.acq.osd.mil/asda/dpc/cp/cyber/docs/safeguarding/NIST-SP-800-171-Assessment-Methodology-Version-1.2.1-6.24.2020.pdf) | Legacy scoring method; CMMC self-assessments now score under 32 CFR 170.24 |
| [DPC Cybersecurity: Safeguarding](https://www.acq.osd.mil/asda/dpc/cp/cyber/safeguarding.html) | DoD's page on 7012 and NIST SP 800-171 implementation |
| [FedRAMP Moderate Equivalency memo](https://dodcio.defense.gov/Portals/0/Documents/Library/FEDRAMP-EquivalencyCloudServiceProviders.pdf) | DoD CIO, December 2023: what "equivalent" means under 7012 |

### Incident reporting

| Resource | Purpose |
|---|---|
| [DC3 DCISE](https://www.dc3.mil/Missions/DIB-Cybersecurity/DIB-Cybersecurity-DCISE/) | Where 7012 incident reports go |
| [DoD ECA program](https://public.cyber.mil/eca/) | How to get the medium assurance certificate required to report |

## Practitioner notes

**Clause numbers changed in February 2026.** 
- The Revolutionary FAR Overhaul moved cybersecurity clauses into FAR Part 40 and DFARS Part 240 through class deviations.
- The codified regulations still show the old numbers, so contracts may cite either. Check which yours uses.

**7012 applies without CMMC.** 
- If your contract has 7012 and you handle covered defense information, you owe NIST SP 800-171, incident reporting, and SPRS scoring today.
- CMMC verifies 7012; it doesn't replace it.

**Read the clause date in your contract.** 
- Clauses get revised (7012 is MAY 2024, 7021 is NOV 2025).
- The version in your contract governs.

**Your SPRS score is a representation.** 
- A Basic Assessment is self-scored from 110 down, and can go negative.
- Submitting it is a statement to the government, with the same False Claims Act exposure as a CMMC affirmation.

**DIBNet is gone.** 
- DoD retired the DIBNet portal in June 2025.
- Reports now go through DC3 DCISE. Older incident response plans that point to dibnet.dod.mil need updating.

**Get the medium assurance certificate before you need it.** 
- You can't submit a report without one, and the 72-hour clock doesn't pause while you buy one.

**The 72-hour clock starts at discovery,** 
- not when you finish investigating.
- Report what you know and update later.

**Preserve images for 90 days.** 
- 7012 requires keeping images of affected systems and relevant monitoring data for at least 90 days after reporting.

**Subcontractors report directly to DoD,** 
- then give the incident number to the prime.

**"FedRAMP Moderate equivalent" is a high bar.** 
- The December 2023 memo requires 100% of the Moderate baseline, assessed by a FedRAMP-recognized 3PAO.
- A SOC 2 report doesn't get you there.

**7012 cloud and 239-7010 cloud are different problems.** 
- 7012 governs cloud you use to store CUI.
- 239-7010 governs cloud you operate for DoD, and brings in DoD's Cloud Computing Security Requirements Guide.
