# GRC, Security Automation & AI Governance Portfolio

Hands-on Governance, Risk, and Compliance (GRC) projects focused on security controls, risk assessment, audit evidence, cloud compliance, policy-as-code, and AI governance engineering.

The portfolio emphasizes a practical workflow:

**Identify risk → Map requirements → Define controls → Evaluate policy → Test → Document evidence → Human review and remediation**

Projects are educational labs, simulations, or sample documentation. They do not represent production deployment, access to a real company's environment, or certification of legal or regulatory compliance.

## Featured Projects

### 1. AI Governance Engineering Lab v2

[Open the AI Governance Engineering Lab v2](./AI-Governance-Engineering-Lab-v2/)

A policy-as-code lab exploring how AI governance requirements can be translated into testable technical controls using Open Policy Agent (OPA) and Rego.

**What it demonstrates**
- AI system inventory and risk register
- Risk methodology, ownership, treatment, and residual-risk tracking
- Policy enforcement for restricted-data privacy, third-party AI vendor approval, fairness validation, and human oversight
- Positive and negative policy test cases
- Vendor assessment and high-level framework mappings to NIST AI RMF and ISO/IEC 42001
- Evidence traceability from requirement to control, policy rule, test, result, and review record
- GitHub Actions workflow for running policy tests when the lab changes

**Recorded validation:** 8 of 8 test cases passed, with 96.30% overall coverage in the documented test run. The 0.80 fairness threshold is a simulated portfolio value, not a regulatory requirement. These results validate the defined scenarios; they do not establish production readiness or regulatory compliance.

### 2. Risk-as-Code GRC Lab

[Open Risk-as-Code](./Risk-As-Code/)

A Python and OPA/Rego lab that turns structured risk-register data into repeatable evaluations and escalation decisions.

**What it demonstrates**
- YAML-based risk data and 5×5 likelihood × impact scoring
- Risk-rating and escalation logic in Python
- Input validation and duplicate-ID detection
- Machine-readable JSON reports
- Optional pipeline failure for open High/Critical risks
- OPA/Rego policy evaluation and unit tests
- SHA-256 File Integrity Monitoring (FIM)
- Separation of risk data, evaluation logic, and policy enforcement

The scoring bands and escalation behavior are the methodology used in this educational lab, not a replacement for an organization's approved enterprise risk methodology.

### 3. AWS S3 Compliance-as-Code Auditor

A Python lab that evaluates simulated AWS S3 configuration data against selected security requirements associated with NIST SP 800-53 and FedRAMP.

Focus areas include encryption, public-access settings, control mapping, remediation recommendations, and unit testing. The infrastructure data is simulated for portfolio use.

### 4. SCF Governance & Control Mapping

A control-mapping lab using the Secure Controls Framework (SCF) to connect governance and technical requirements with practical evidence and follow-up actions.

Topics include policy publishing, exception management, privileged-access reviews, MFA, AI governance, and evidence mapping.

### 5. Vendor Security Review

A simulated third-party risk assessment for a fictional analytics vendor. It considers independent security assurance, data protection, access management, compensating controls, and remediation needs. Findings are documented as a learning exercise, not a real procurement decision.

### 6. Linux Server Audit

A baseline review of a simulated Linux server focused on SSH and privileged-access settings. The lab identifies configuration issues, relates them to security criteria, and documents corrective-action recommendations.

### 7. Corporate Access Control Policy

A sample policy covering MFA, least privilege, access approvals, and periodic access reviews. It demonstrates how common security requirements can be translated into practical policy language.

### 8. Business Data & Systems Integrity Lab

A simulated business-systems investigation using SQL and Python to identify cross-system data inconsistencies, document business risk, and demonstrate remediation and validation workflows.

## Tools & Technologies

- **Programming and data:** Python, SQL, JSON, YAML
- **Policy-as-Code:** Open Policy Agent (OPA), Rego
- **Testing and integrity:** Python unit tests, OPA tests, SHA-256 file integrity checks
- **Automation:** GitHub Actions
- **Governance and risk:** NIST SP 800-53, NIST CSF, NIST AI RMF, ISO/IEC 42001 concepts, SOC 2, FedRAMP, Secure Controls Framework (SCF)
- **Technical areas:** AWS security concepts, Linux configuration, access control, third-party risk, audit evidence, remediation tracking

Framework references and mappings are high-level portfolio examples. They do not imply that an individual control or policy rule satisfies an entire framework requirement.

## GRC Workflow

Across the projects, the general workflow is:

1. **Identify** the system, business context, and risk.
2. **Assess** likelihood, impact, and relevant requirements.
3. **Define** controls, owners, and expected evidence.
4. **Evaluate** structured records and policy conditions.
5. **Test** expected allow, deny, and exception scenarios.
6. **Document** results, limitations, and evidence.
7. **Review and remediate** findings with responsible human owners.
8. **Reassess** when conditions or risks change.

## Portfolio Boundaries

These projects are intended to demonstrate practical learning and repeatable technical workflows. Sample records, simulated infrastructure, and policy thresholds are illustrative. Automated outputs are decision support—not proof of control effectiveness or a certification of compliance. Human review and organization-specific validation remain necessary before real-world use.
