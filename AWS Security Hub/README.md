# AWS Security Hub

AWS's service for checking configuration against security standards and bringing security findings into one place. As of 2025 it's two related services with nearly the same name.

*Last reviewed October 2026.*

## Two services, one name

| Service | What it does |
|---|---|
| Security&nbsp;Hub&nbsp;CSPM | The original Security Hub, renamed. Runs automated checks against standards, aggregates findings in ASFF format, and requires AWS Config |
| Security&nbsp;Hub | A newer service, generally available since late 2025. Correlates findings from Security Hub CSPM, GuardDuty, Inspector, and Macie into prioritized risks, using the OCSF format |

They're complementary. CSPM answers "is it configured correctly?" and the new Security Hub answers "which risk matters most?"

## Standards in Security Hub CSPM

| Standard | Notes |
|---|---|
| AWS&nbsp;Foundational&nbsp;Security&nbsp;Best&nbsp;Practices | AWS's own baseline; the usual starting point |
| CIS&nbsp;AWS&nbsp;Foundations&nbsp;Benchmark | v5.0.0, v3.0.0, v1.4.0, v1.2.0. See the CIS page in this guide |
| NIST&nbsp;SP&nbsp;800&#8209;53&nbsp;Rev.&nbsp;5 | Federal control catalog |
| NIST&nbsp;SP&nbsp;800&#8209;171&nbsp;Rev.&nbsp;2 | CUI requirements; covers only those that can be checked automatically |
| PCI&nbsp;DSS | Payment card environments |
| Service&#8209;managed&nbsp;(Control&nbsp;Tower) | Detective controls governed from AWS Control Tower |

## Primary sources

| Resource | Purpose |
|---|---|
| [Standards&nbsp;reference](https://docs.aws.amazon.com/securityhub/latest/userguide/standards-available.html) | Every standard Security Hub CSPM supports |
| [NIST&nbsp;SP&nbsp;800&#8209;171&nbsp;standard](https://docs.aws.amazon.com/securityhub/latest/userguide/standards-reference-nist-800-171.html) | Which controls map to which 800-171 requirements |
| [Security&nbsp;Hub&nbsp;FAQs](https://aws.amazon.com/security-hub/faqs/) | AWS's explanation of the two services and how findings differ |
| [AWS&nbsp;Security&nbsp;Services&nbsp;Best&nbsp;Practices](https://aws.github.io/aws-security-services-best-practices/guides/security-hub/) | AWS's own deployment and configuration guidance |

## Practitioner notes

**Know which one you're reading about.** 
- Most tutorials and older documentation that say "Security Hub" mean what's now Security Hub CSPM.

**A passing score isn't compliance.** 
- AWS states its standards don't guarantee compliance with any framework or audit.
- The NIST SP 800-171 standard skips every requirement that needs a manual check.

**AWS Config is the dependency.** 
- CSPM's checks rely on Config recording the right resource types.
- Missing recording means missing findings, and Config is often the larger cost.

**Enable it across the organization.** 
- Use a delegated administrator account and central configuration, so every account and Region gets the same standards automatically.

**Turn off what doesn't apply, with a reason.**
- Disabling irrelevant controls cuts noise. Record why, so an auditor sees a decision and not a gap.

**Use consolidated control findings.** 
- When several standards share a control, this setting produces one finding instead of duplicates.

**Route findings somewhere.**
- Send findings through EventBridge to a ticketing system or chat channel. A dashboard nobody checks isn't monitoring.

**Available in GovCloud.**
- Security Hub CSPM and its standards run in the AWS GovCloud (US) regions.
