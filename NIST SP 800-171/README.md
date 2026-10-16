# NIST SP 800-171

Protecting Controlled Unclassified Information in Nonfederal Systems and Organizations
- The security requirements contractors implement under DFARS 252.204-7012, and the standard CMMC Level 2 assesses against.

## Which revision applies

| Revision | Status |
|---|---|
| Rev. 2 (Feb 2020) | **Required for DoD contracts.** 110 requirements, 14 families. DoD Class Deviation 2024-O0013 pins 7012 to Rev. 2, and 32 CFR 170 incorporates it for CMMC. |
| Rev. 3 (May 2024) | Current NIST version. 97 requirements, 17 families, aligned to SP 800-53 Rev. 5. Not yet required by DoD. |

## Primary sources

| Resource | Purpose |
|---|---|
| [SP&nbsp;800‑171&nbsp;Rev.&nbsp;2](https://csrc.nist.gov/pubs/sp/800/171/r2/upd1/final) | The 110 requirements. Also hosts the CUI SSP template and CSV/XLSX versions. |
| [SP&nbsp;800‑171A&nbsp;(June&nbsp;2018)](https://csrc.nist.gov/pubs/sp/800/171/a/final) | Assessment objectives for Rev. 2 |
| [DoD&nbsp;Assessment&nbsp;Methodology](https://www.acq.osd.mil/asda/dpc/cp/cyber/docs/safeguarding/NIST-SP-800-171-Assessment-Methodology-Version-1.2.1-6.24.2020.pdf) | How DoD scores Rev. 2 for SPRS |
| [SP&nbsp;800‑171&nbsp;Rev.&nbsp;3](https://csrc.nist.gov/pubs/sp/800/171/r3/final) | The current NIST revision |
| [SP&nbsp;800‑172](https://csrc.nist.gov/pubs/sp/800/172/final) | Enhanced requirements against advanced persistent threats; the basis for CMMC Level 3 |
| [NIST&nbsp;CUI&nbsp;project&nbsp;page](https://csrc.nist.gov/Projects/protecting-controlled-unclassified-information) | All CUI series publications, Rev. 2 to Rev. 3 change analysis, FAQs |
## Practitioner notes

**NIST shows Rev. 2 as superseded.**
- It's still the one DoD contracts require.
- Don't let the banner on NIST's site send you to Rev. 3.

**Learn Rev. 3, implement Rev. 2.**
- DoD published organization-defined parameter values for Rev. 3 in April 2025 to prepare for a transition.
- Until the class deviation is rescinded, Rev. 2 is what you're scored on.

**Requirements aren't weighted equally.** 
- The DoD Assessment Methodology assigns 1, 3, or 5 points per requirement.
- Fix the 5-pointers first.

**FIPS-validated, not FIPS-compliant.** 
- 3.13.11 requires FIPS-validated cryptography for protecting CUI.
- Check the module's [CMVP certificate](https://csrc.nist.gov/projects/cryptographic-module-validation-program/validated-modules/search), not the vendor's marketing.

**MFA covers more than admins.**
- 3.5.3 requires MFA for network access to non-privileged accounts too, not just privileged and remote access.

**The SSP is a requirement itself.** 
- 3.12.4 requires a system security plan.
- No SSP means you can't be assessed, automatic FAIL

**Use the spreadsheets.** 
- NIST publishes Rev. 2 and 800-171A in CSV and XLSX.
- They're the fastest way to build an objective-level tracker, outside of a continuous compliance platform (recommended)

**800-172 is for critical programs.**
- It applies only when a contract designates CUI tied to a critical program or high value asset.
