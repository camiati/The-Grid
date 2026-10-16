# FedRAMP 20x

The new FedRAMP path. Providers demonstrate security outcomes through Key Security Indicators, backed by automated, machine-readable evidence, in place of control-by-control narratives.

## Status

| Item | Detail |
|---|---|
| Governing&nbsp;rules | Consolidated Rules for 2026, published June 2026 |
| Available&nbsp;classes | Class A (opened August 3, 2026); Classes B and C (opened August 31, 2026) |
| Class&nbsp;D | Not yet available through 20x; a pilot is planned |
| Sponsor | Not required; Classes A to C go through Program Certification directly with FedRAMP |

## Certification classes

| Class | Notes |
|---|---|
| Class&nbsp;A | Replaced FedRAMP Ready. Transitional, with an initial path built on SOC 2 Type II |
| Class&nbsp;B | Roughly the old Low |
| Class&nbsp;C | Roughly the old Moderate |
| Class&nbsp;D | Roughly the old High; Rev5 only for now |

FedRAMP says classes describe how much security information a provider shares and how often, not how secure an offering is.

## Primary sources

| Resource | Purpose |
|---|---|
| [Consolidated&nbsp;Rules&nbsp;for&nbsp;2026](https://fedramp.gov/2026) | The current ruleset and definitions |
| [20x&nbsp;certification&nbsp;rules](https://fedramp.gov/2026/providers/20x/rules/fedramp-certification/) | How 20x certifications are obtained and maintained |
| [Important&nbsp;dates](https://fedramp.gov/2026/timeline/) | Official transition timeline |
| [Machine&#8209;readable&nbsp;rules](https://github.com/FedRAMP/rules) | The rules as JSON, the source of truth for tooling |
| [Notice&nbsp;0007](https://fedramp.gov/notices/0007) | FedRAMP's explanation of Class A and its SOC 2 starting point |
| [OMB&nbsp;M&#8209;24&#8209;15](https://www.fedramp.gov/2026/authority/m-24-15/) | The July 2024 OMB memo behind the program reset |
| [FedRAMP&nbsp;Marketplace](https://www.fedramp.gov/marketplace/) | Current certification status of cloud offerings |

## Practitioner notes

**20x doesn't satisfy DoD yet.** 
- At its July and August 2026 town halls, Cyber AB leadership relayed the Department of War's position that 20x does not currently meet DFARS 7012 or CMMC requirements.
- Written guidance is expected. Until then, DoD contractors should rely on Rev5 Moderate or equivalency for CUI.

**Pick one path.** 
- Providers can't pursue both Rev5 and 20x Program Certification for the same offering.

**Automation is the entry fee.** 
- 20x expects persistent, automated validation of security posture.
- Providers without infrastructure-as-code and continuous monitoring will struggle.

**Class A is a starting point.** 
- FedRAMP describes it as transitional, meant to be replaced by a Class B, C, or D certification.

**Read the rules repo, not summaries.**
- The JSON rules on GitHub are the implementation source of truth, and they change faster than any guide.
