# GRC-001 — SCF-Based MFA Control Assessment

## Lab Overview

**Organization:** Caribbean Health Services (fictional)  
**Lab type:** Simulated GRC control assessment  
**Framework reference:** Secure Controls Framework (SCF) 2026.2  
**Control under assessment:** IAC-06 — Multi-Factor Authentication (MFA)  
**Assessment status:** Preliminary — evidence validation pending

This lab demonstrates a practical control-assessment workflow: define scope, connect threats and risks to a control, identify evidence, assess implementation, document a gap, recommend remediation, and define retesting criteria.

> **Scope and transparency:** Caribbean Health Services, its environment, and all scenario facts are fictional. This is a self-directed learning exercise, not a real audit, compliance opinion, or assessment of a production environment. No actual organizational evidence was obtained or validated. SCF identifiers and evidence request descriptions are recorded from the workbook used during the exercise; users of other SCF versions should verify identifiers and wording against their own copy.

---

## 1. Assessment Overview

**Organization:** Caribbean Health Services (fictional)  
**Assessment type:** Cybersecurity control assessment  
**Framework:** Secure Controls Framework (SCF) 2026.2  
**Control:** IAC-06 — Multi-Factor Authentication (MFA)

### Assessment scope

Remote employee access to organizational systems, including Microsoft 365 and cloud infrastructure.

The scope is focused on applicable remote authentication paths. It does not assume that every device, physical interaction, network connection, or operational technology (OT) component requires MFA. Applicability depends on the system, access method, architecture, operational requirements, and approved organizational policies.

### Assessment objective

Evaluate whether MFA is implemented and enforced for applicable remote employee access, identify potential control gaps, and determine what evidence would be needed to validate implementation and effectiveness.

---

## 2. Control and Risk Context

### 2.1 Control identification

- **SCF control ID:** IAC-06
- **Control name:** Multi-Factor Authentication (MFA)
- **Framework reference:** SCF 2026.2

MFA strengthens authentication by requiring more than one authentication factor before access is granted to applicable systems.

### 2.2 Associated risk

- **Risk catalog entry:** Access Control Risk

The risk description in the exercise's Risk Catalog covers unauthorized access. In this scenario, inadequate authentication controls could increase the likelihood of unauthorized individuals gaining access to organizational systems, applications, or sensitive information.

Because the organization processes Protected Health Information (PHI), unauthorized access could expose sensitive healthcare information or affect system integrity and business operations.

### 2.3 Threat context

- **Threat classification:** Man-made
- **Threat category:** MT2 — Cybersecurity and Technology

MT2 is a broad category covering cybersecurity requirements for information and communications technology, including technical vulnerabilities and weaknesses that may negatively affect confidentiality, integrity, availability, and/or safety (CIAS).

MT2 provides broad threat context. It should not be treated as a specific credential-theft event or as proof that a particular attack occurred.

### 2.4 Relationship between threat, risk, and control

The threat category describes the broader cybersecurity environment. The Access Control Risk describes the organization's exposure to unauthorized access. IAC-06 is a safeguard intended to reduce that exposure by strengthening authentication.

These are related but distinct concepts:

- **Threat context:** MT2 — Cybersecurity and Technology.
- **Risk:** Access Control Risk / unauthorized access.
- **Control:** IAC-06 — MFA.
- **Scenario weakness:** MFA is enabled for administrators but is not enforced for all applicable remote employees.

---

## 3. Evidence Collection and Review

### 3.1 Evidence collection objective

Obtain sufficient, relevant documentation to determine whether MFA is configured, enforced, and operating as intended for the applicable remote employee population.

### 3.2 SCF Evidence Request List references

The following entries were identified in the Evidence Request List during the exercise:

| ERL ID | Evidence request description | Relevance to this assessment |
|---|---|---|
| E-DCH-08 | Documented evidence identifying authorized users and processes acting on behalf of authorized users. | Supporting evidence to establish the population of authorized users and accounts in scope. |
| E-CPL-07 | Documented evidence of data stewardship being assigned and communicated to individuals entrusted with sensitive and/or regulated data. | Governance context; not direct evidence of MFA implementation. |
| E-CPL-08 | Documented evidence of control testing to ensure cybersecurity controls function as expected. | Relevant to determining whether MFA controls are tested for effectiveness. |

These references help organize evidence collection, but they do not by themselves prove that MFA is configured or enforced.

### 3.3 Additional technical evidence to request

The following are assessment-specific evidence requests. They are not assigned SCF ERL IDs in this lab unless an exact matching entry is verified in the workbook.

1. MFA enforcement policies and configuration for in-scope applications and remote access paths.
2. User MFA coverage report identifying applicable remote employee accounts and their enforcement status.
3. Conditional Access policies or equivalent identity-provider rules showing the users, applications, and conditions covered.
4. List of accounts or access paths excluded from MFA, with documented justification and approval.
5. Relevant authentication logs or reports demonstrating that MFA challenges are enforced.
6. Results of control tests or sample-based verification.

### 3.4 Evidence validation criteria

Evidence should be reviewed to determine:

- Whether the population of applicable remote users and accounts is defined.
- Whether MFA is required by configuration, rather than merely available as an optional feature.
- Whether the relevant applications and access paths are covered.
- Whether exclusions are documented, justified, approved, and periodically reviewed.
- Whether testing demonstrates that MFA operates as intended.

**Evidence status:** Identified for request and review. No technical evidence has been received or independently validated in this simulated exercise.

---

## 4. Assessment Results and Identified Control Gaps

### 4.1 Scenario information

The fictional scenario provides the following facts:

- MFA is enabled for administrator accounts.
- MFA is not enforced for all remote employees.

### 4.2 Preliminary implementation status

**Preliminary status: Partially Implemented**

Based on the scenario facts, MFA is implemented for administrator accounts but is not consistently enforced for all applicable remote employee access within the defined scope.

This is a scenario-based preliminary assessment, not a conclusion based on independently inspected technical evidence.

### 4.3 Identified control gap

MFA is not consistently enforced for all applicable remote employee accounts accessing organizational systems.

This weakness could increase the likelihood that a person with compromised employee credentials could access organizational resources without completing an additional authentication factor.

### 4.4 Potential business impact

Potential consequences include:

- Unauthorized access to Microsoft 365 or cloud infrastructure.
- Exposure or unauthorized disclosure of PHI.
- Compromise of employee accounts.
- Disruption of business operations.
- Increased cybersecurity, regulatory, and reputational exposure.

No actual compromise or breach is asserted by this assessment.

### 4.5 Assessment observations

| Observation | Current assessment |
|---|---|
| MFA enabled for administrators | Implemented according to the scenario |
| MFA enforced for all applicable remote employees | Not consistently implemented according to the scenario |
| MFA enforcement configuration | Pending technical verification |
| User MFA coverage | Pending evidence |
| MFA exceptions | Pending evidence |
| Control effectiveness testing | Pending evidence |

### 4.6 Preliminary conclusion

Based on the scenario information, IAC-06 is preliminarily assessed as **Partially Implemented** within the defined scope. The lack of consistent MFA enforcement for applicable remote employee access represents a control gap.

The status must be validated against technical evidence before it is treated as a verified assessment conclusion.

---

## 5. Risk Analysis and Recommendations

### 5.1 Risk analysis

Incomplete MFA enforcement for applicable remote employee access may increase exposure to unauthorized access. If employee credentials are stolen, guessed, or compromised through phishing or another attack, the absence of an additional authentication factor may make unauthorized access easier.

Because the fictional organization processes PHI, unauthorized access could affect confidentiality and potentially disrupt business operations.

- **Associated risk:** Access Control Risk.
- **Threat context:** MT2 — Cybersecurity and Technology.
- **Control:** IAC-06 — MFA.

### 5.2 Recommended corrective actions

1. **Define applicability:** Confirm which remote users, applications, systems, and access paths are in scope for MFA.
2. **Expand enforcement:** Require MFA for all applicable remote employee accounts accessing organizational systems.
3. **Review identity policies:** Identify accounts, applications, and access paths not covered by MFA enforcement.
4. **Manage exceptions:** Document, justify, approve, and periodically reassess any exceptions.
5. **Validate implementation:** Obtain configuration and coverage reports demonstrating that MFA is enforced for the intended population.
6. **Test the control:** Perform periodic tests to identify gaps, exclusions, or unintended bypasses.

MFA should not be indiscriminately applied to every physical interaction or device. OT and other specialized environments require a separate applicability assessment based on their architecture, operational constraints, and available authentication mechanisms.

### 5.3 Remediation ownership

- **Responsible department:** Information Technology / IT Security.
- **Supporting departments:** Human Resources and Compliance, as appropriate.
- **Remediation owner:** To be assigned by organizational management.
- **Target completion date:** To be established by management based on risk and operational requirements.

### 5.4 Expected outcome

MFA is consistently enforced for applicable remote access within the approved scope; exceptions are documented and governed; and technical evidence demonstrates implementation and testing.

---

## 6. Validation, Retesting, and Closure

### 6.1 Remediation validation

After corrective actions are implemented, IT should provide updated evidence showing that MFA is enforced for the applicable remote employee population and relevant access paths.

The assessor reviews the evidence to determine whether the identified gap has been adequately addressed.

### 6.2 Retesting procedures

1. Review updated MFA enforcement policies and configuration.
2. Examine user coverage reports to verify that applicable accounts are covered.
3. Review exclusions and confirm that exceptions are documented and approved.
4. Select a sample of applicable accounts and verify enforcement through configuration review and/or controlled testing.
5. Review authentication logs or test results to confirm that MFA requirements operate as intended.
6. Document test population, sample selection, results, exceptions, and limitations.

### 6.3 Remediation acceptance criteria

The finding may be considered remediated when:

- MFA is enforced for all applicable remote employee accounts within the defined scope.
- Exceptions are documented, justified, approved, and periodically reviewed.
- Technical evidence supports the implementation.
- Retesting demonstrates that the control operates as intended.
- Remaining deficiencies are documented and assigned corrective actions.

### 6.4 Finding closure

The assessor evaluates the retesting results and determines whether the gap has been resolved. If sufficient evidence supports successful remediation, the finding may be closed under the organization's approval process. If deficiencies remain, the finding stays open or is updated to reflect outstanding issues.

### 6.5 Assessment closure record

| Field | Status |
|---|---|
| Control ID | IAC-06 |
| Initial assessment status | Partially Implemented (scenario-based) |
| Remediation status | Pending |
| Retesting status | Not performed |
| Final control status | Pending validation |
| Finding closure date | Not applicable / pending |
| Assessor | Not assigned |
| Management approval | Pending |

---

## 7. Lab Lessons and Professional Considerations

This exercise demonstrates the relationship between control requirements, risk context, evidence collection, assessment, remediation, and retesting.

Key lessons:

- A control must be assessed within a clearly defined scope.
- A threat category, a risk, and a control are different concepts.
- An evidence request is not the same as evidence received.
- A policy or verbal assertion is not sufficient proof of technical enforcement.
- A control can be partially implemented without being fully effective.
- Recommendations must account for system architecture and operational constraints; conventional MFA is not applicable to every physical task or every OT device.
- AI can help identify issues and draft recommendations, but responsible people must validate context, approve consequential decisions, and remain accountable for outcomes.

**Lab limitation:** This is a fictional, scenario-based exercise. No real organization, production system, user population, or technical configuration was examined. The preliminary status is based only on the supplied scenario facts.
