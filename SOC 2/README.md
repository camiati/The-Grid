# SOC 2

An attestation report from an independent CPA firm on a service organization's controls, evaluated against the AICPA Trust Services Criteria.
The common way SaaS and service providers show customers their security posture.

## Primary sources

The AICPA publishes both documents for free, but requires a free account to download.

| Resource | Purpose |
|---|---|
| [2017&nbsp;Trust&nbsp;Services&nbsp;Criteria](https://www.aicpa-cima.com/resources/download/2017-trust-services-criteria-with-revised-points-of-focus-2022) | The criteria (TSP Section 100), with the 2022 revised points of focus |
| [SOC&nbsp;2&nbsp;Description&nbsp;Criteria](https://www.aicpa-cima.com/resources/download/get-description-criteria-for-your-organizations-soc-2-r-report) | What the system description in the report must cover (DC Section 200) |

## Report types

| Type | What it covers |
|---|---|
| Type&nbsp;1 | Design of controls at a single point in time |
| Type&nbsp;2 | Design and operating effectiveness over a period, commonly 3 to 12 months |

## Practitioner notes

**It's an attestation, not a certification.** 
- A CPA firm issues an opinion.
- There's no such thing as "SOC 2 certified."

**Security is required; the rest are optional.**
- The common criteria (CC1 to CC9) are in every SOC 2.
- Add availability, confidentiality, processing integrity, or privacy only when customers need them.

**Customers want Type 2.**
- A Type 1 is a reasonable first step, but most security reviews ask for a Type 2.

**You write the controls.** 
- The TSC are criteria, not controls.
- The auditor tests the controls you describe, so don't describe controls you can't evidence for the whole period.

**Points of focus aren't requirements.** 
- They're considerations for designing controls.
- You don't need a control for each one.

**Exceptions aren't failures.** 
- A tested control with exceptions still appears in the report with the auditor's notes.
- A qualified opinion is the outcome to avoid.

**Auditors sample from populations.**
- For Type 2, expect requests for full lists (every change, every new hire, every terminated user) and then samples from them.
- Your systems of record need to produce those lists cleanly.

**Know your subservice organizations.**
- Most companies carve out their cloud provider, which means relying on that provider's SOC 2.
- Collect those reports annually.

**Read the CUECs.** 
- Vendors' reports list complementary user entity controls, the things they assume you do. Those become your responsibilities.

**Bridge letters cover the gap.**
- When a customer asks for current assurance between report periods, a bridge letter from management covers the time since the last period ended.

**SOC 3 is the public version.**
- A general-use summary without the detailed test results, suitable for a website.

**SOC 2 isn't FedRAMP equivalency.**
- For DoD cloud requirements under DFARS 7012, a SOC 2 report doesn't establish FedRAMP Moderate equivalency.
