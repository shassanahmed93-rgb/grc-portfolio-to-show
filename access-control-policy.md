# Access Control Policy

| | |
|---|---|
| **Policy ID** | ISMS-POL-003 |
| **Organisation** | Meridian Provisions Group (fictional) |
| **Owner** | Chief Information Security Officer (CISO) |
| **Approver** | Executive Committee |
| **Version** | 0.1 DRAFT |
| **Effective date** | On approval |
| **Review cycle** | Annually, and after any significant access-related incident |
| **ISO/IEC 27001:2022** | A.5.15, A.5.16, A.5.17, A.5.18, A.6.5, A.8.2, A.8.3, A.8.5, plus A.5.3, A.5.19, A.6.7, A.8.4, A.8.15, A.8.20 |

> **Drafting note.** Requirements marked **(register)** come directly from treatment plans and KRI targets in the Enterprise Risk Register. All other numeric values (for example session lengths and review cycles) are proposed standards that the approver must confirm against business needs.

---

## 1. Purpose

This policy ensures that only authorised people, devices and systems can reach Meridian information and technology, and only to the extent their role requires. It responds to the identity and access risks in the register, where stolen or misused credentials are the most likely route to ransomware, data theft and fraud.

## 2. Scope

The policy applies to:

- all employees, contractors, temporary staff, interns and third parties who access Meridian systems;
- all **human accounts** and **non-human accounts** (service accounts, API keys, automation, machine identities);
- corporate IT, cloud, SaaS, the customer and dealer portal, and **operational technology (OT)** at all 14 plants;
- access from any location, including home, remote and plant sites.

## 3. Policy principles

1. **Least privilege.** People receive the minimum access needed for their current role.
2. **Need to know.** Access to confidential data (personal data, formulations, financials) requires a documented business reason.
3. **Deny by default.** Access that has not been explicitly granted is denied.
4. **Segregation of duties.** No one person can both initiate and approve a sensitive transaction or change.
5. **Accountability.** Every account belongs to a named person or a named owner. **Shared accounts are prohibited.**
6. **Verify explicitly.** Access depends on identity, device health and context, not on network location.
7. **Time-bound.** Elevated, contractor and third-party access expires automatically.

## 4. Roles and responsibilities

| Role | Responsibility |
|---|---|
| CISO | Owns this policy; reports access KRIs to the Risk Committee |
| Head of Identity & Access / Identity & Access Manager | Operates the identity platform, MFA, PAM and access reviews |
| Chief Information Officer, Chief Digital Officer | Ensure systems integrate with the identity provider and enforce this policy |
| Head of OT Security, COO | Apply this policy to plant systems and vendor access |
| System and data owners | Approve access requests and complete access reviews |
| Line managers | Request access, confirm role changes, and report leavers promptly |
| HR (Chief People Officer) | Provides authoritative joiner, mover and leaver data |
| Procurement and Vendor Risk | Ensure contracts contain access, audit and notification terms |
| All users | Protect credentials, report suspected compromise, never share accounts |

## 5. Account lifecycle (joiner, mover, leaver)

| Stage | Requirement |
|---|---|
| **Joiner** | Access is granted by role template, with approval from the manager and the data owner for sensitive systems. No access before the HR start record exists. |
| **Mover** | Access from the old role is removed within **5 working days** of the change; the new role is approved on request. This is the main control against privilege creep (R-026). |
| **Leaver** | Accounts are disabled **within 24 hours** of the HR leave date through automated integration between the HR system and the identity provider **(register, R-025)**; immediate disablement is required for involuntary exits. |
| **Dormant** | Accounts unused for **90 days** are disabled; accounts unused for 180 days are deleted after owner confirmation **(register KRI: dormant accounts > 90 days)**. |
| **Target KRI** | Leaver accounts still active more than 7 days: **0** **(register)**. |

## 6. Authentication

1. **Multi-factor authentication (MFA)** is mandatory for all remote access, email, VPN, SSO, cloud consoles, SaaS applications, privileged access and the portal for staff users.
2. **Phishing-resistant MFA** (FIDO2 security keys or passkeys) is required for finance, HR, administrators and other high-risk users **(register, R-013, R-024)**. The goal is to extend it to all staff over time.
3. Where push-based MFA remains in use, **number matching and location context** must be enabled on every service, not only the VPN **(register, R-024)**. Repeated denied prompts lock the account and alert the SOC.
4. **Passwords** are at least 14 characters, are checked against a breached-password list, and are never reused across systems. Forced periodic change is not required unless compromise is suspected. Password managers are approved and encouraged.
5. **Customer and dealer portal:** breached-password screening is enabled, and passkeys and optional MFA are offered to dealers **(register, R-028)**.
6. **Session controls:** device-bound sessions for sensitive applications; admin sessions are short-lived; legacy authentication protocols are disabled **(register, R-030, R-054)**.
7. Authentication secrets are never stored in documents, chat or source code **(see section 9)**.

## 7. Privileged access

| Requirement | Detail |
|---|---|
| Separate admin accounts | Administrators use dedicated accounts for admin work, never for email or browsing |
| Tiered administration | Domain, server and workstation administration are separated; the tiered model is completed **(register, R-023)** |
| Privileged Access Management (PAM) | **100% of privileged accounts** are held in the PAM vault with session recording **(register KRI, R-023)** |
| Just-in-time (JIT) access | Standing administrator rights are removed in favour of time-limited elevation **(register, R-023)** |
| Break-glass accounts | Held offline, monitored, tested and **rotated after each use and at least every 90 days** **(register, R-023)** |
| Cloud administration | Least-privilege cloud roles through cloud entitlement management; unused permissions are removed **(register, R-052)** |
| Four-eyes approval | Destructive actions on production systems require a second approver; mass-deletion alerts are enabled **(register, R-060)** |
| Review | Privileged access is reviewed **quarterly** |

## 8. Role-based access and segregation of duties

- Access is granted through **role-based access control (RBAC)** templates, not individual permissions, wherever the system allows.
- **ERP and finance roles** are checked against a segregation-of-duties rule set. Conflicts are either removed or approved with a compensating control by the CFO. A full SoD conflict analysis is run **(register, R-026)**.
- Payments above $50,000 require dual approval, and changes to supplier bank details require call-back verification **(register, R-011, R-059)**.

## 9. Non-human accounts and secrets

1. Every service account, API key and automation credential has a **named owner**, a documented purpose and an entry in the **service-account register** **(register, R-027)**.
2. Secrets are stored in the approved **secrets vault** with **automatic rotation**. Long-lived static credentials are prohibited for new systems.
3. Secrets older than **365 days** are a reportable exception, and the target is zero **(register KRI, R-027)**.
4. **Hardcoded secrets** in source code are prohibited. Secret scanning is mandatory in all repositories and exposed secrets are revoked and rotated immediately **(register, R-050)**.
5. Default credentials on devices, including OT and IoT equipment, are changed before connection **(register, R-070)**.

## 10. Contractors, vendors and third-party access

| Requirement | Detail |
|---|---|
| Sponsor | Every third-party account has a named internal sponsor who is accountable for it |
| Expiry | **Mandatory expiry date** on every contractor account, matching the contract end date **(register, R-029)** |
| No shared accounts | Shared and generic accounts are banned, including on plant sites **(register, R-029)** |
| MSP access | Just-in-time access with **session recording**, and contractual right-to-audit **(register, R-067)** |
| OT vendor access | **Only through the OT jump server**, with an approval workflow, multi-factor authentication and session recording; no direct or shared remote-access tools **(register, R-068)** |
| Contracts | Security schedule covering access, breach notification (within 48 hours) and audit rights **(register, R-073)** |
| Subcontractors | Critical vendors disclose subcontractors, and access terms flow down **(register, R-074)** |

## 11. Remote and hybrid access

1. Access to sensitive applications is allowed only from **managed, compliant devices**. Compliance is checked at each session through conditional access **(register, R-013, R-030)**.
2. The legacy VPN is replaced over time by **zero-trust network access (ZTNA)**; access depends on user, device and application, not on network location **(register, R-014, R-032)**.
3. Personal devices (BYOD) may use only a **virtual desktop**, with no local data storage **(register, R-014)**.
4. Target KRI: at least **98% of devices MDM-compliant**, and 100% of sensitive-app sessions from compliant devices **(register)**.

## 12. Network and plant access

- Access between network zones (user, server, data centre, plant) is permitted only where there is a business need. Critical systems are **micro-segmented** and admin protocols are restricted between zones **(register, R-034)**.
- **IT/OT segmentation** is mandatory at all 14 plants. Plants not yet segmented must apply compensating controls until completion **(register, R-012)**.
- Network access control (NAC) is extended to plants. Unmanaged devices are blocked **(register, R-037)**.

## 13. Access review and recertification

| Access type | Frequency | Reviewer |
|---|---|---|
| Privileged and administrator access | Quarterly | System owner and CISO |
| Finance and ERP access | Quarterly **(register, R-026)** | CFO delegate |
| Access to confidential data (personal data, formulations) | Semi-annually | Data owner |
| Standard business access | Annually | Line manager |
| Contractor and vendor accounts | Quarterly | Sponsor |
| Service accounts and API keys | Semi-annually | Account owner |

Reviewers must either approve or remove each entitlement. Reviews that are not completed within 14 days trigger escalation to the reviewer's executive. The outcome of every review is retained as evidence.

## 14. Logging and monitoring

Authentication events, privilege use, MFA denials, admin actions, vendor sessions and access changes are logged centrally and monitored by the SOC. Alerts include: repeated MFA denials, impossible travel, new privileged group membership, creation of mailbox forwarding rules, use of break-glass accounts, and bulk downloads by leavers. Logs are protected from alteration.

## 15. Exceptions

Exceptions must be documented in the risk register, approved by the CISO (and by the risk owner for High or Critical risks), time-limited to a maximum of **90 days**, and supported by compensating controls. Exceptions are reported at the monthly security review.

## 16. Compliance and enforcement

Violations may lead to access removal and disciplinary action under the HR process (A.6.4). Suspected access misuse must be reported through the incident process (see the Incident Response Policy, ISMS-POL-004). Compliance is monitored through the KRIs below and tested in internal audit.

## 17. Metrics (aligned with register KRIs)

| Metric | Target | Linked risk |
|---|---|---|
| % privileged accounts in PAM | 100% | R-023 |
| Standing admin accounts | Trend to 0 | R-023 |
| Leaver accounts active > 7 days | 0 | R-025 |
| Dormant accounts > 90 days | Trend to 0 | R-025 |
| % users on phishing-resistant MFA (high-risk groups) | 100% | R-013, R-024 |
| Phishing click rate | < 5% | R-013 |
| % service accounts with owner and rotation | 100% | R-027 |
| Secrets older than 365 days | 0 | R-027 |
| Open SoD conflicts / overdue access reviews | 0 overdue | R-026 |
| Contractor accounts without expiry; shared accounts in use | 0 | R-029 |
| % sensitive-app sessions from compliant devices | 100% | R-030 |
| % MSP sessions recorded; standing MSP privileges | 100%; 0 | R-067 |
| % vendor sessions via approved OT gateway | 100% | R-068 |

## 18. Related documents

- Incident Response Policy (ISMS-POL-004)
- Remote Working Policy (to be refreshed, register R-014)
- Acceptable Use and AI Acceptable Use Policies
- Enterprise Risk Register v1.0; Annex A control mapping

## 19. Document control

| Version | Date | Author | Description |
|---|---|---|---|
| 0.1 | 2026-10-19 | GRC analyst | First draft from Risk Register v1.0 |

| Approval | Name | Signature | Date |
|---|---|---|---|
| CISO | | | |
| Chief Executive Officer or delegate | | | |
