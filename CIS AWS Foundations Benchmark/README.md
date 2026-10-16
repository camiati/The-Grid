# CIS AWS Foundations Benchmark

The Center for Internet Security's consensus-based configuration baseline for AWS accounts. It covers account-level settings across identity, storage, logging, monitoring, and networking.

## Versions

| Item | Version |
|---|---|
| Latest&nbsp;CIS&nbsp;release | v7.1.0 |
| Latest&nbsp;in&nbsp;Security&nbsp;Hub&nbsp;CSPM | v5.0.0 (also supports v3.0.0, v1.4.0, v1.2.0) |

## Profile levels

| Level | Intent |
|---|---|
| Level&nbsp;1 | Practical baseline for every account, with minimal operational impact |
| Level&nbsp;2 | Defense in depth for sensitive environments; may add cost or complexity |

## Primary sources

| Resource | Purpose |
|---|---|
| [CIS&nbsp;AWS&nbsp;Benchmarks](https://www.cisecurity.org/benchmark/amazon_web_services) | Download the Foundations benchmark and the service-specific AWS benchmarks |
| [CIS&nbsp;Benchmarks&nbsp;list](https://www.cisecurity.org/cis-benchmarks) | All CIS benchmarks, for operating systems and other platforms |
| [CIS&nbsp;in&nbsp;Security&nbsp;Hub&nbsp;CSPM](https://docs.aws.amazon.com/securityhub/latest/userguide/cis-aws-foundations-benchmark.html) | Which versions AWS supports and which controls map to each |

## Practitioner notes

**Free for non-commercial use.** 
- CIS publishes the benchmark PDFs free for non-commercial use.
- Other formats and tooling come with CIS SecureSuite membership.

**Check the version gap.**
- CIS has moved past the newest version Security Hub CSPM scans against.
- Know which version your scanner checks and which version your auditor or customer expects.

**Scanners don't cover everything.**
- Some recommendations are marked manual and can't be checked automatically.
- Those need evidence from you.

**Foundations is only the account layer.** 
- CIS publishes separate AWS benchmarks for compute, database, storage, and end-user compute services.

**Document your exceptions.**
- If you deliberately don't follow a recommendation, record the risk acceptance.
- An unexplained failed check looks like a gap; a documented decision looks like a program.

**It maps to configuration requirements.**
- A CIS baseline is solid evidence for NIST SP 800-171's security configuration settings requirement (3.4.2) and SOC 2 configuration management criteria.

**Works in GovCloud.**
- Security Hub CSPM's CIS standard is available in the AWS GovCloud (US) regions.
