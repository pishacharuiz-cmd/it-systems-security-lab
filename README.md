# IT Systems & Security Lab

Hands-on projects across **IT operations, data integrity, security controls, IT audit, risk automation, and AI governance**. This portfolio demonstrates how I investigate technical and business problems, validate records and configurations, test controls, automate repeatable checks, and document findings and remediation.

**Practical workflow:** Understand the environment → Identify the issue or risk → Validate evidence → Test data, configuration, or controls → Recommend remediation → Validate results → Document.

> **Scope and transparency:** These are educational labs, simulations, and sample documentation. They do not represent production deployments or access to a real company's environment. Framework mappings are illustrative and do not certify compliance.

## Featured Projects

### 1. IT General Controls (ITGC) Audit Lab
[View project](./ITGC-Audit-Lab/)

A simulated ITGC review using evidence files, control-testing procedures, findings, risk assessment, and remediation recommendations.

- Reviews user access, privileged access, change management, and user termination
- Uses sample CSV evidence and PowerShell scripts to identify control exceptions
- Documents test populations, exceptions, risks, corrective actions, and retesting considerations
- Demonstrates the workflow: **Control → Evidence → Testing → Finding → Risk → Remediation → Retest**

**Why it matters:** Shows practical IT control testing and evidence-based analysis—not just framework summaries. All organizations, records, and findings in the lab are fictional or simulated.

### 2. Business Data & Systems Integrity Lab
[View project](./business-data-systems-integrity-lab/)

A simulated investigation of customer records moving between a source CRM and a downstream operational database, using SQL and Python.

- Checks for status and balance mismatches, missing records, duplicates, and stale downstream data
- Uses SQL joins and validation queries to identify inconsistencies
- Creates a local SQLite database from sample CSV data and generates a findings report
- Connects technical discrepancies to potential business impact, corrective action, and validation

**Why it matters:** Relevant to application support, business systems, data operations, and technical analyst roles where accurate records and reliable integrations matter.

### 3. AI Governance Engineering Lab
[View project](./AI-Governance-Engineering-Lab-v2/)

Uses Open Policy Agent (OPA) and Rego to demonstrate how selected AI governance requirements can be translated into testable policy rules.

- AI system inventory, risk register, risk treatment, and residual-risk tracking
- Policy checks for restricted-data privacy, third-party AI vendor approval, a configured fairness gate, and human oversight
- Positive and negative tests, sample inputs, and evidence links from requirements to controls, rules, tests, and review records
- GitHub Actions workflow for policy testing
- High-level mapping to NIST AI RMF and ISO/IEC 42001 concepts

**Documented test evidence:** 8/8 test cases passed and 96.30% overall coverage in the recorded local run. The 0.80 fairness threshold is a simulated lab value, not a regulatory requirement. These results apply to the defined scenarios and do not establish production readiness or compliance.

### 4. Risk-as-Code
[View project](./Risk-As-Code/)

A Python and OPA/Rego workflow for evaluating structured risk data and producing repeatable results.

- YAML-based risk register with 5×5 likelihood-and-impact scoring
- Risk-rating and escalation logic, input validation, and duplicate-ID detection
- Machine-readable JSON reports and an optional nonzero exit when open High/Critical risks require escalation
- OPA/Rego policy evaluation and unit tests
- SHA-256 file-integrity monitoring
- Separation of risk data, evaluation logic, and policy enforcement

Scoring bands and escalation rules are the lab's illustrative methodology, not a substitute for an organization's approved risk process.

### 5. AWS S3 Compliance-as-Code Auditor
[View project](./AWS%20S3%20Compliance-as-Code%20Auditor%20NIST%20SP%20800-53%20%20FedRAMP/)

A Python lab that evaluates **simulated** AWS configuration data against selected security requirements associated with NIST SP 800-53 and FedRAMP.

- Checks encryption and public-access settings
- Connects selected checks to control references
- Documents findings and remediation recommendations
- Includes unit tests for the evaluation logic

This lab does not connect to or assess a live AWS account.

### 6. PCI DSS Automated Compliance Lab
[View project](./pci-dss-automated-compliance-lab/)

A collection of small scripts and sample configurations illustrating technical checks related to payment-environment security.

- Simulated cloud configuration checks for unrestricted ingress and S3 public-access settings
- SHA-256 file-integrity monitoring example
- Authentication-log parsing for repeated failed login attempts
- References selected PCI DSS requirements

The scripts use sample or local data and are learning examples, not a validated PCI DSS assessment tool or evidence of compliance.

## Additional Projects

- **[SCF Governance & Control Mapping](./scf-governance-mapping/)** — connects selected governance and technical requirements to evidence requests, exceptions, and follow-up activities.
- **[Basic SQL Lab](./Basic%20SQL%20Lab/)** — foundational queries for data extraction, filtering, aggregation, and basic compliance checks.
- **[Linux Server Audit](./policies/linux-server-audit.md)** — sample baseline review focused on SSH and privileged-access settings.
- **[Vendor Security Review](./policies/vendor-risk-assessment.md)** — simulated third-party risk review covering assurance, data protection, access, findings, and remediation.
- **[Corporate Access Control Policy](./policies/Corporate_Access_Control%20Policy.md)** — sample policy language covering MFA, least privilege, access approvals, and periodic access reviews.
- **[Business Data & Systems Integrity Lab](./business-data-systems-integrity-lab/)** — detailed SQL/Python workflow for reconciliation, findings, and evidence.
- **[AI governance policy example](./policies/ai_governance/policy.rego)** — a separate Rego example for expressing selected governance conditions as policy.

## Skills Demonstrated

| Area | Examples in this portfolio |
|---|---|
| IT operations and controls | Access reviews, privileged access, change management, termination controls, Linux baseline review |
| Data and systems integrity | SQL validation, cross-system reconciliation, discrepancy analysis, SQLite, Python reporting |
| Audit and GRC | Evidence review, control testing, exception documentation, risk assessment, remediation, control mapping |
| Automation | Python, OPA, Rego, unit tests, JSON, YAML, GitHub Actions, SHA-256 integrity checks |
| Cloud and technical security | Simulated S3 configuration checks, encryption, public-access settings, log analysis |
| AI governance | AI inventory, risk assessment, vendor review, human oversight, policy-as-code, NIST AI RMF and ISO/IEC 42001 concepts |

## Tools & Framework References

**Tools:** Python · SQL · Linux · PowerShell (in the ITGC lab) · SQLite · Open Policy Agent (OPA) · Rego · GitHub Actions · JSON · YAML

**Frameworks and reference material:** NIST SP 800-53 · NIST Cybersecurity Framework (CSF) · NIST AI RMF · ISO/IEC 42001 concepts · SOC 2 concepts · FedRAMP · PCI DSS · Secure Controls Framework (SCF)

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

These projects demonstrate learning, structured investigation, and repeatable technical workflows. Sample records, simulated infrastructure, and policy thresholds are illustrative. Automated outputs support human decisions; they are not proof of control effectiveness, a production security assessment, or a certification of compliance. Real-world use requires authorization, environment-specific validation, and review by responsible owners.
