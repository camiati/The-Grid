# CMMC

Cybersecurity Maturity Model Certification. DoD's program for verifying that contractors protect FCI and CUI. Program rules are in 32 CFR Part 170; contract requirements come through DFARS 252.204-7021. Phase 1 began November 10, 2025.

*Last reviewed October 2026.*

## Current status (October 2026)

On July 13, 2026, the Department of War (DoD) suspended CMMC Phase 2, which would have made Level 2 (C3PAO) assessments the default in applicable contracts starting November 10, 2026. Later phases are on hold while a CMMC Reform Task Force reviews the program.

| Item | Status |
|---|---|
| Phase&nbsp;1&nbsp;self&#8209;assessments | In effect. Level 1 and Level 2 (Self) requirements still appear in solicitations; scores and affirmations go in SPRS |
| Phase&nbsp;2&nbsp;and&nbsp;later | Suspended. Contracting officers are removing C3PAO and DIBCAC requirements from solicitations and existing contracts |
| DFARS&nbsp;7012&nbsp;and&nbsp;NIST&nbsp;SP&nbsp;800&#8209;171 | Unchanged |
| C3PAO&nbsp;assessments | Still being conducted; primes may require them independently |
| Reform&nbsp;Task&nbsp;Force | Report delivered to the DoW CIO in September 2026; not yet public |

## Start here

- [CMMC Level Determination brief](https://dodcio.defense.gov/cmmc/Resources-Documentation/): how a contract's CMMC level is chosen (on the DoD CIO resources page)
- [Scoping Guide – Level 2](https://dodcio.defense.gov/Portals/0/Documents/CMMC/ScopingGuideL2.pdf): what's in and out of the assessment boundary
- [Assessment Guide – Level 2](https://dodcio.defense.gov/Portals/0/Documents/CMMC/AssessmentGuideL2.pdf): requirement-by-requirement assessment guidance
- [32 CFR Part 170](https://www.ecfr.gov/current/title-32/subtitle-A/chapter-I/subchapter-G/part-170): the regulation, especially §170.19 (scoping), §170.21 (POA&Ms), §170.22 (affirmations), §170.24 (scoring)

## Primary sources

### Regulation and contract clauses

| Resource | Purpose |
|---|---|
| [32 CFR Part 170](https://www.ecfr.gov/current/title-32/subtitle-A/chapter-I/subchapter-G/part-170) | CMMC program rule |
| [DFARS Subpart 204.75](https://www.acquisition.gov/dfars/subpart-204.75-cybersecurity-maturity-model-certification) | How contracting officers apply CMMC |
| [DFARS 252.204-7021](https://www.acquisition.gov/dfars/252.204-7021-contractor-compliance-cybersecurity-maturity-model-certification-level-requirements.) | CMMC contract clause: status, affirmations, flowdown |
| [DFARS 252.204-7012](https://www.acquisition.gov/dfars/252.204-7012-safeguarding-covered-defense-information-and-cyber-incident-reporting.) | Safeguarding clause: NIST SP 800-171, 72-hour incident reporting, cloud requirements |
| [DFARS Subpart 204.73](https://www.acquisition.gov/dfars/subpart-204.73-safeguarding-covered-defense-information-and-cyber-incident-reporting) | Policy behind 7012 and the SPRS assessment (252.204-7019/-7020) |

### Standards

| Resource | Purpose |
|---|---|
| [NIST SP 800-171 Rev. 2](https://csrc.nist.gov/pubs/sp/800/171/r2/upd1/final) | The 110 requirements assessed at Level 2 |
| [NIST SP 800-171A (June 2018)](https://csrc.nist.gov/pubs/sp/800/171/a/final) | Assessment objectives for each requirement |

### DoD guidance

| Resource | Purpose |
|---|---|
| [DoD CIO CMMC Resources & Documentation](https://dodcio.defense.gov/cmmc/Resources-Documentation/) | Official source for current guides, including the hashing guide |
| [Assessment Guide – Level 3](https://dodcio.defense.gov/Portals/0/Documents/CMMC/AssessmentGuideL3.pdf) / [Scoping Guide – Level 3](https://dodcio.defense.gov/Portals/0/Documents/CMMC/ScopingGuideL3.pdf) | Level 3 (DIBCAC) guidance |
| [DPC Cybersecurity: Safeguarding](https://www.acq.osd.mil/asda/dpc/cp/cyber/safeguarding.html) | DoD guidance on 7012 and NIST SP 800-171 |

### Ecosystem

| Resource | Purpose |
|---|---|
| [The Cyber AB](https://cyberab.org/) | Accreditation body; its Marketplace is the authoritative C3PAO directory |
| [CUI Registry](https://www.archives.gov/cui/registry/category-list.html) | Official list of CUI categories |

## Practitioner notes

**Scoping is the project.** Level 2 has five asset categories: CUI Assets, Security Protection Assets, Contractor Risk Managed Assets, Specialized Assets, and Out-of-Scope. Decide early between an enclave and enterprise-wide scope.

**Integrations pull systems into scope.** Map data flows at the field level for anything that might touch CUI.

**It's Rev. 2, not Rev. 3.** CMMC Level 2 assesses against SP 800-171 Rev. 2.

**800-171A shows as withdrawn on NIST's site.** 
- It still applies. 32 CFR 170 incorporates the June 2018 version by reference.

**Assessors test objectives.**
- The 110 requirements break into about 320 objectives.
- A requirement is MET only when all its objectives are.

**Security tools and providers are in scope.**
- SIEM, EDR, identity, and MSPs are typically Security Protection Assets.
- Get a customer responsibility matrix from each provider.

**Cloud has its own bar.**
- A cloud provider handling CUI must meet FedRAMP Moderate or equivalent under 7012.
- DoD's December 2023 equivalency memo makes "equivalent" hard to meet.

**POA&Ms are narrow.** 
- §170.21 limits which requirements qualify, sets a minimum score, and requires closeout within 180 days.

**The affirmation is personal.** 
- §170.22 requires a senior official to affirm compliance at assessment and annually.
- A false affirmation carries False Claims Act exposure.

**Freeze your evidence.** 
- Keep a versioned copy of exactly what the assessor saw.

**Products aren't "CMMC certified."** 
- Organizations get CMMC status. Tools don't.

**Know whether you have FCI, CUI, or both.** 
- Level 1 covers FCI under FAR 52.204-21.
- Over-scoping by assuming everything is CUI is common.
- Check the CUI Registry and your contract clauses.

## Templates

NIST publishes a CUI SSP template, plus SP 800-171 Rev. 2 and 800-171A in CSV and XLSX, on the [SP 800-171 Rev. 2 page](https://csrc.nist.gov/pubs/sp/800/171/r2/upd1/final).
