# AWS Well-Architected: Security Pillar

AWS's guidance for designing and operating secure workloads. It's one of six pillars in the AWS Well-Architected Framework: guidance, not an auditable standard.

## Design principles

| Principle | In practice |
|---|---|
| Strong&nbsp;identity&nbsp;foundation | Least privilege, separation of duties, centralized identity, no long-term static credentials |
| Traceability | Monitor, alert, and audit actions and changes in real time |
| Security&nbsp;at&nbsp;all&nbsp;layers | Defense in depth, from network edge to application code |
| Automate&nbsp;security | Controls defined and managed as code in version-controlled templates |
| Protect&nbsp;data | Classify data, then encrypt, tokenize, and restrict access by sensitivity |
| Keep&nbsp;people&nbsp;away&nbsp;from&nbsp;data | Reduce direct and manual access to data |
| Prepare&nbsp;for&nbsp;events | Incident management and investigation processes ready before you need them |

## Primary sources

| Resource | Purpose |
|---|---|
| [Security&nbsp;Pillar](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html) | The full pillar: foundations, identity, detection, infrastructure, data protection, incident response, application security |
| [Well&#8209;Architected&nbsp;Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) | All six pillars |
| [AWS&nbsp;Security&nbsp;Reference&nbsp;Architecture](https://docs.aws.amazon.com/prescriptive-guidance/latest/security-reference-architecture/welcome.html) | Where each AWS security service belongs in a multi-account environment |
| [Shared&nbsp;Responsibility&nbsp;Model](https://aws.amazon.com/compliance/shared-responsibility-model/) | What AWS secures versus what you secure |
| [Cloud&nbsp;Adoption&nbsp;Framework](https://docs.aws.amazon.com/whitepapers/latest/overview-aws-cloud-adoption-framework/welcome.html) | AWS's broader framework, including its security perspective |

## Practitioner notes

**Start with accounts.** 
- Separate accounts by environment and function.
- The Security Reference Architecture's dedicated security tooling and log archive accounts are the pattern to copy.

**Get rid of IAM users.**
- Federate through your identity provider into IAM Identity Center and use roles.
- Long-term access keys are the credential attackers find first.

**Lock down the root user.** 
- MFA on, no access keys, credentials stored where nobody uses them day to day.

**Enabled isn't monitored.** 
- GuardDuty, CloudTrail, and VPC Flow Logs only help if findings reach someone.
- Confirm alerts route to a person or queue, and test it.

**Restrict default security groups.** 
- Every VPC's default security group should allow nothing.
- It's one of the most common findings in AWS security reviews.

**Responsibility shifts by service.**
- You patch the operating system on EC2; AWS does on Lambda.
- Read the shared responsibility model per service

**Turn on S3 Block Public Access at the account level.**
- It overrides bucket-level mistakes.

**Use it for evidence mapping.** 
- The pillar's practices line up with SOC 2 logical access and monitoring criteria and NIST SP 800-171 access control and audit requirements.
- Map them once and reuse the evidence.
