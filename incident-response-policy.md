# Incident Response Policy

| | |
|---|---|
| **Policy ID** | ISMS-POL-004 |
| **Organisation** | Meridian Provisions Group (fictional) |
| **Owner** | Chief Information Security Officer (CISO) |
| **Approver** | Executive Committee |
| **Version** | 0.1 DRAFT |
| **Effective date** | On approval |
| **Review cycle** | Annually, after every Severity 1 or 2 incident, and after each major exercise |
| **ISO/IEC 27001:2022** | A.5.24, A.5.25, A.5.26, A.5.27, A.5.28, A.6.8, plus A.5.5, A.5.29, A.5.30, A.5.31, A.5.34, A.8.15, A.8.16 |

> **Drafting note.** Requirements marked **(register)** come from treatment plans and KRIs in the Enterprise Risk Register. Other values (such as response-time targets) are proposed standards for management to confirm.

---

## 1. Purpose

This policy sets out how Meridian prepares for, detects, responds to and learns from information security incidents. Its aim is to limit harm to people, production, customers and data, to meet legal notification duties, and to recover quickly.

It addresses the incident-related risks in the register: ransomware on corporate IT (R-061, the only residual Critical risk) and on plant OT (R-012), failed recovery (R-045), immature response capability (R-058), delayed detection (R-057) and missed breach-notification deadlines (R-064).

## 2. Scope

The policy covers all information security incidents affecting Meridian information, IT, cloud, OT, products and services, whether the cause is malicious, accidental or a third-party failure. It applies to all employees, contractors, suppliers and service providers (including MSPs and OT vendors) who handle Meridian systems or data.

## 3. Definitions

| Term | Meaning |
|---|---|
| **Event** | Any observable occurrence relevant to security |
| **Incident** | An event that compromises, or is likely to compromise, confidentiality, integrity or availability |
| **Personal data breach** | An incident leading to accidental or unlawful destruction, loss, alteration, disclosure of, or access to, personal data |
| **Major incident** | Any Severity 1 or Severity 2 incident |
| **IR Lead** | Incident Response Lead, who coordinates the response |
| **CIRT** | Cyber Incident Response Team (see section 5) |

## 4. Principles

1. **Report fast, blame later.** Reporting in good faith is never penalised.
2. **Contain before you investigate fully,** but preserve evidence.
3. **People and safety first,** then production, then data, then reputation.
4. **One incident commander** makes decisions for each incident.
5. **Notify on time.** Legal clocks start when Meridian becomes aware, and the IR playbook tracks them.
6. **Learn.** Every major incident ends with a lessons-learned review.

## 5. Roles and responsibilities

| Role | Responsibility |
|---|---|
| **CISO** | Policy owner; incident executive sponsor; decides escalation to the Executive Committee |
| **Incident Response Lead (IR Lead)** | Incident commander; runs the CIRT, timeline, decisions log and playbooks |
| **Head of Security Operations / SOC** | Detects, triages and contains; provides 24×7 coverage through the managed detection and response (MDR) provider **(register, R-057)** |
| **Head of IT Operations** | Recovery of IT services, backups and restoration |
| **Head of OT Security / COO** | Plant safety, OT containment and manual-mode production |
| **General Counsel and Privacy Counsel** | Legal privilege, regulatory notification, contractual notices |
| **Data Protection Officer** | Personal data breach assessment and supervisory authority liaison |
| **Chief Financial Officer / Group Risk Manager** | Payment decisions, cyber insurance notification **(register, R-075)** |
| **Chief People Officer** | Insider incidents, employee communication |
| **Corporate Communications** | Internal and external statements; approved spokespeople only |
| **Vendor Risk Manager / Chief Procurement Officer** | Third-party incident coordination |
| **External IR and forensics retainer** | Surge capacity and forensics **(register, R-061)** |
| **All staff** | Report suspected incidents immediately |

## 6. Preparation

1. **Plan and playbooks.** Playbooks exist for at least: ransomware (IT), ransomware (OT/plant), personal data breach, business email compromise and payment fraud, cloud account compromise, insider threat, third-party/MSP compromise, DDoS, and lost or stolen device.
2. **Contacts.** An on-call roster, a regulator contact list, a legal and insurer contact list and the retainer details are kept current and available offline.
3. **Logging and detection.** Cloud and SaaS logs are onboarded to the SIEM and critical assets send logs; the KRI is the share of critical assets sending logs and the mean time to detect **(register, R-057)**.
4. **Backups and recovery.** Tier-1 systems have defined recovery time and recovery point objectives. **Immutable backup copies** are kept in a separate account, and **restore tests run quarterly** for tier-1 systems **(register, R-045, R-061)**.
5. **Endpoint coverage.** EDR is deployed on 100% of endpoints **(register, R-061)**.
6. **Communications.** Out-of-band communication channels are ready in case email and chat are unavailable. Pre-drafted notification templates exist per jurisdiction **(register, R-064)**.
7. **Training and exercises.** See section 12.

## 7. Severity classification

Severity uses the impact scale in the risk register's Scoring sheet so that incidents and risks share one language.

| Severity | Description | Typical examples | Response target | Escalation |
|---|---|---|---|---|
| **Sev 1 – Critical** | Severe impact: multiple plants or key products down for more than 2 weeks, or loss above $100M, or licence to operate at risk; confirmed large-scale personal data breach | Ransomware encrypting ERP; ransomware halting several plants; domain admin compromise with data theft | Incident declared **within 1 hour** of triage; CIRT convened immediately | CEO, Executive Committee and Board chair informed **within 4 hours** |
| **Sev 2 – High** | Major impact: plant or key product line down 3 days to 2 weeks, $25M to $100M, formal regulatory action likely | Ransomware in one plant; breach of customer database; MSP compromise | CIRT convened **within 2 hours** | CISO and relevant executives **within 4 hours** |
| **Sev 3 – Moderate** | Moderate impact: degraded production 1 to 3 days, regulatory inquiry or reportable incident, $5M to $25M | Single compromised account with limited access; malware on a few endpoints; DDoS with partial impact | Triage **within 4 hours**; handled by SOC and IR Lead | CISO daily summary |
| **Sev 4 – Low** | Minor impact: short disruption, self-identified minor non-compliance | Misdirected email with no sensitive data; blocked phishing | Next business day | Weekly report |

If it is unclear whether an incident is Sev 2 or 3, treat it as the higher severity until the facts are clear. **Any incident involving personal data, plant operations or payments is escalated for legal and operational review regardless of size.**

## 8. Incident lifecycle

### 8.1 Detect and report
- Anyone who notices a possible incident reports it **immediately** to the Service Desk or security mailbox, or by phone for urgent cases (A.6.8).
- Automated alerts from the SOC are triaged by analysts using playbooks.
- Third parties must notify Meridian **within 48 hours** of becoming aware of an incident affecting Meridian data **(register, R-073)**; critical MSPs and OT vendors should be held to a shorter timeframe in contract.

### 8.2 Triage and decide (A.5.25)
The SOC records the time of detection, assigns a provisional severity, and the IR Lead confirms the classification and declares the incident. The **time to declare an incident** is measured as a KRI **(register, R-058)**. A **decision log** records every significant decision and who made it.

### 8.3 Contain
- Isolate affected endpoints and accounts, revoke tokens and sessions, disable compromised credentials, block malicious indicators.
- **Ransomware (IT):** isolate infected segments, disable affected accounts and shares, protect backups first, and preserve volatile evidence.
- **OT:** safety comes first. The Head of OT Security and the plant manager decide whether to **disconnect IT/OT links** and switch to **manual-mode production** under rehearsed plans **(register, R-012)**. Vendor remote access to plants is suspended.
- **Cloud and SaaS:** rotate keys, remove malicious OAuth grants and mailbox rules, restrict public storage.

### 8.4 Investigate and preserve evidence (A.5.28)
Evidence is collected using forensically sound methods, with chain of custody, and under direction of Legal where litigation or regulatory action is possible. Systems are not wiped before images are taken unless safety or business continuity requires it, and that exception is recorded.

### 8.5 Eradicate and recover
- Remove attacker access, rebuild affected systems from known-good sources and **verify backups are clean before restoring**.
- Recover in priority order agreed by the business (safety systems, plant control, ERP, then others).
- Monitor closely for re-infection after recovery.

### 8.6 Post-incident review (A.5.27)
A review is held **within 10 working days** of closing a Sev 1 or Sev 2 incident, and covers root cause, timeline, what worked, what failed, and corrective actions. Actions are tracked in the risk register and the risk is rescored if the control assessment changes.

## 9. Legal, regulatory and contractual notification (A.5.31, A.5.34)

1. The **Privacy Counsel and the DPO** assess every incident involving personal data. A **72-hour clock** (GDPR Article 33) starts when Meridian becomes aware of a breach, and is shown on the IR playbook **(register, R-064)**.
2. Where there is a high risk to individuals, affected people are notified without undue delay (Article 34).
3. Other jurisdictions and regulators are checked against the **jurisdiction template library**. Requirements differ across the 9 countries in which Meridian operates, and the Legal team keeps this library current.
4. Customers, retailers, insurers and law enforcement are notified according to contracts and law. **The insurer is notified within the policy period** and before any ransom decision.
5. **Ransom payment** is never decided by the incident team alone. A decision requires the CEO, General Counsel and CFO, takes sanctions and legal advice into account, and is reported to the Board. Payment is not the default.
6. Only authorised spokespeople communicate externally. Staff must not speak to media or on social media about an incident.

## 10. Third-party incidents

When an incident involves a supplier, MSP or vendor, the Vendor Risk Manager joins the CIRT, access for that party is reviewed or suspended, and contractual notification and audit rights are exercised **(register, R-066, R-067)**. The incident informs the next vendor risk assessment.

## 11. Business continuity linkage

Major incidents are assessed for business continuity impact. Where required, the continuity plan (ISO 22301) and the disaster recovery runbooks are invoked, and decisions on manual production, alternate sites and customer communication are made by the COO and the CIRT (A.5.29, A.5.30).

## 12. Testing, training and improvement

| Activity | Frequency | Owner |
|---|---|---|
| Executive tabletop exercise | **Twice a year** **(register, R-058)** | IR Lead |
| Ransomware tabletop (IT and OT) | At least annually and before peak season **(register, R-061)** | IR Lead, Head of OT Security |
| Manual-mode production drill at plants | Annually per plant, phased **(register, R-012)** | COO, Head of OT Security |
| Backup restore tests (tier-1) | **Quarterly** **(register, R-045)** | Head of IT Operations |
| Notification drill (including the 72-hour clock) | Annually **(register, R-064)** | Privacy Counsel |
| Payment fraud and deepfake drill | Annually **(register, R-011, R-059)** | Treasury Controller |
| Cloud and DR failover test | Annually **(register, R-071)** | Head of Cloud Platform |
| Playbook review | Annually and after each major incident | IR Lead |
| Staff awareness on reporting | Annual training and quarterly simulations | CISO |

Lessons from exercises and real incidents feed the register, playbooks and this policy.

## 13. Metrics and reporting

| Metric | Target or use | Linked risk |
|---|---|---|
| Mean time to detect (MTTD) | Trend downward | R-057 |
| % critical assets sending logs | 100% | R-057 |
| Time to declare incident | Within 1 hour of triage (Sev 1) | R-058 |
| Exercises completed vs planned | 100% | R-058 |
| Time to regulatory decision in exercises | Within 24 hours | R-064 |
| % endpoints with EDR | 100% | R-061 |
| Recovery time in restore test vs RTO | Within RTO | R-061 |
| Backup success rate; restore test pass rate | ≥ 99%; 100% | R-045 |
| Third-party notifications received within contract time | 100% | R-073 |
| Incidents by severity and root cause | Reported monthly | All |

The CISO reports these monthly to the Executive Committee and quarterly to the Risk Committee and Board.

## 14. Compliance

Failure to report an incident, deliberate concealment, or interference with an investigation may lead to disciplinary action (A.6.4). Exceptions to this policy need CISO approval and are recorded in the risk register.

## 15. Related documents

- Access Control Policy (ISMS-POL-003)
- Playbooks: ransomware (IT), ransomware (OT), personal data breach, BEC and payment fraud, MSP compromise
- Business continuity and disaster recovery plans
- Enterprise Risk Register v1.0; Annex A control mapping

## 16. Document control

| Version | Date | Author | Description |
|---|---|---|---|
| 0.1 | 2026-10-19 | GRC analyst | First draft from Risk Register v1.0 |

| Approval | Name | Signature | Date |
|---|---|---|---|
| CISO | | | |
| General Counsel | | | |
| Chief Executive Officer or delegate | | | |
