# IT Systems & Security Lab

Hands-on projects across **IT operations, systems integrity, security controls, risk automation, and AI governance**. This portfolio shows how I investigate technical and business problems, validate data and configurations, translate requirements into controls, test results, and document remediation.

**Practical workflow:** Understand the environment → Identify the issue or risk → Validate evidence → Test controls or data → Recommend remediation → Document results.

> **Scope and transparency:** These are educational labs, simulations, and sample documentation. They do not represent production deployments or access to a real company's environment. Framework mappings are illustrative and do not certify compliance.

## Featured Projects

### AI Governance Engineering Lab
[View project](./AI-Governance-Engineering-Lab-v2/)

Uses Open Policy Agent (OPA) and Rego to demonstrate how AI governance requirements can be translated into testable policy rules.

- AI system inventory, risk register, ownership, treatment, and residual-risk tracking
- Policy checks for restricted-data privacy, third-party AI vendor approval, fairness validation, and human oversight
- Positive and negative test cases, with evidence links from requirements to controls, rules, tests, and review records
- GitHub Actions workflow to run policy tests when the lab changes
- High-level mapping to NIST AI RMF and ISO/IEC 42001 concepts

**Documented test run:** 8/8 test cases passed and 96.30% overall coverage. The 0.80 fairness threshold is a simulated lab value, not a regulatory requirement. These results apply only to the defined scenarios and do not establish production readiness or compliance.

### Risk-as-Code
[View project](./Risk-As-Code/)

A Python and OPA/Rego workflow for evaluating structured risk data and producing repeatable results.

- YAML-based risk register with 5×5 likelihood-and-impact scoring
- Risk-rating and escalation logic, input validation, and duplicate-ID detection
- Machine-readable JSON reports and optional pipeline failure for open High/Critical risks
- OPA/Rego policy evaluation and unit tests
- SHA-256 file-integrity monitoring
- Separation of risk data, evaluation logic, and policy enforcement

Scoring bands and escalation rules are the lab's own illustrative methodology, not a substitute for an organization's approved risk process.

### AWS S3 Compliance-as-Code Auditor

A Python lab that checks **simulated** AWS S3 configuration data against selected security requirements associated with NIST SP 800-53 and FedRAMP.

- Encryption and public-access configuration checks
- Control mapping and remediation recommendations
- Repeatable evaluation and unit testing

### Business Data & Systems Integrity Lab

A simulated business-systems investigation using SQL and Python.

- Identify inconsistencies across data sources
- Validate records and investigate discrepancies
- Describe potential business impact
- Document corrective actions and post-remediation validation

### Linux Server Audit

A baseline review of a simulated Linux server focused on SSH and privileged-access settings. Identifies configuration concerns, relates findings to security criteria, and documents corrective-action recommendations.

### SCF Governance & Control Mapping

Maps selected governance and technical requirements to controls, evidence, and follow-up actions. Topics include policy publishing, exceptions, privileged-access reviews, MFA, AI governance, and evidence mapping.

### Vendor Security Review

A simulated third-party risk review for a fictional analytics vendor, covering independent assurance, data protection, access management, compensating controls, findings, and remediation needs.

### Corporate Access Control Policy

Sample policy language covering MFA, least privilege, access approvals, and periodic access reviews, demonstrating how security expectations can be expressed as operational requirements.

## Skills Demonstrated

| Area | Practical examples |
|---|---|
| IT and systems | Linux configuration review, access controls, systems integrity, troubleshooting and validation |
| Data and scripting | Python, SQL, JSON, YAML, input validation, repeatable reports |
| Security automation | OPA, Rego, unit tests, policy evaluation, GitHub Actions, SHA-256 integrity checks |
| Risk and controls | Risk registers, likelihood/impact scoring, control mapping, evidence, findings, remediation tracking |
| Cloud security concepts | Simulated AWS S3 configuration checks, encryption, public-access settings |
| Governance and AI risk | NIST AI RMF and ISO/IEC 42001 concepts, AI inventory, vendor review, human oversight |

## Tools & Framework References

**Tools:** Python · SQL · Linux · Open Policy Agent (OPA) · Rego · GitHub Actions · JSON · YAML

**Frameworks and reference material:** NIST SP 800-53 · NIST Cybersecurity Framework (CSF) · NIST AI RMF · ISO/IEC 42001 concepts · SOC 2 concepts · FedRAMP · Secure Controls Framework (SCF)

Framework references and mappings are high-level learning examples. A mapping does not mean that one policy, test, or control satisfies an entire framework requirement.

## How I Approach a Problem

1. **Understand** the system, business process, and expected outcome.
2. **Assess** the available records, configuration, requirements, and potential impact.
3. **Verify** the issue with evidence rather than assuming a root cause.
4. **Test** the data, configuration, or policy against defined expectations.
5. **Recommend or apply** an appropriate corrective action within the authorized scope.
6. **Validate** the result and check whether the issue remains.
7. **Document** evidence, limitations, ownership, and follow-up needs.

## Portfolio Boundaries

The projects demonstrate learning, structured investigation, and repeatable technical workflows. Sample records, simulated infrastructure, and policy thresholds are illustrative. Automated outputs support human decisions; they are not proof of control effectiveness, a production security assessment, or a certification of compliance. Real-world use requires authorization, environment-specific validation, and review by responsible owners.
