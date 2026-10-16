# AWS GovCloud (US)

Isolated AWS Regions (US-West and US-East) for regulated workloads. Administered only by AWS personnel who are U.S. citizens, with accounts limited to vetted U.S. persons.

*Links verified October 2026.*

## GovCloud vs. commercial US Regions

| Item | Commercial&nbsp;US&nbsp;East/West | GovCloud&nbsp;(US) |
|---|---|---|
| FedRAMP | Class C (formerly Moderate) | Class D (formerly High) |
| DoD&nbsp;impact&nbsp;levels | IL2 | IL2, IL4, IL5 |
| Export&nbsp;control | Not designed for ITAR or EAR data | Supports ITAR and EAR compliance |
| Accounts | Standard AWS accounts | Separate account and credentials, U.S. persons only |

## Primary sources

| Resource | Purpose |
|---|---|
| [What&nbsp;is&nbsp;GovCloud](https://docs.aws.amazon.com/govcloud-us/latest/UserGuide/whatis.html) | AWS's overview and user guide |
| [GovCloud&nbsp;vs.&nbsp;standard&nbsp;Regions](https://docs.aws.amazon.com/govcloud-us/latest/UserGuide/govcloud-differences.html) | Endpoints, credentials, and service differences |
| [GovCloud&nbsp;compliance](https://docs.aws.amazon.com/govcloud-us/latest/UserGuide/govcloud-compliance.html) | Compliance programs GovCloud supports |
| [Services&nbsp;in&nbsp;scope:&nbsp;FedRAMP](https://aws.amazon.com/compliance/services-in-scope/FedRAMP/) | Which services are FedRAMP-covered in each environment |
| [AWS&nbsp;FedRAMP&nbsp;offering&nbsp;information](https://aws.amazon.com/compliance/fedramp/cloud-service-offering-information/) | AWS's FedRAMP environments, classes, and package access |
| [AWS&nbsp;and&nbsp;ITAR](https://aws.amazon.com/compliance/itar/) | How GovCloud supports ITAR compliance |
| [GovCloud&nbsp;FAQs](https://aws.amazon.com/govcloud-us/faqs) | Account setup, access, and authorization questions |

## Practitioner notes

**CUI doesn't automatically require GovCloud.** 
- DFARS 7012 requires FedRAMP Moderate or equivalent for cloud holding CUI, and in-scope services in commercial US East/West meet that.
- GovCloud is usually driven by export-controlled data, DoD IL4 or IL5, FedRAMP High, or a contract requirement. Confirm against your contracts.

**Coverage is per service.** 
- Only services listed as in scope count.
- Check the services-in-scope page before designing a CUI workload, in either environment.

**Expect feature lag.** 
- Not every AWS service or feature is available in GovCloud, and new ones often arrive later.
- Check availability before committing to an architecture.

**It's a separate partition.** 
- GovCloud uses its own account, credentials, and endpoints.
- Plan identity federation, tooling, and pipelines for it separately.

**There's no ITAR certification.** 
- GovCloud supports ITAR compliance by restricting who administers it.
- You're still responsible for making sure only U.S. persons can access your export-controlled data.

**Pull AWS's package for your SSP.**
- AWS's FedRAMP package and customer responsibility matrix are available through AWS Artifact.
- Use them to document which controls you inherit.

**Security tooling works there.**
- Security Hub CSPM and its standards, including CIS and NIST SP 800-171, run in GovCloud.
- See the Security Hub and CIS pages in this guide.

**Related pages:** 
- CMMC, DFARS, and FedRAMP Rev5 in this guide cover the requirements GovCloud is usually chosen to meet.
