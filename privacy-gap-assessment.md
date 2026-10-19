# Privacy Gap Assessment

| | |
|---|---|
| **Organisation** | Meridian Provisions Group (fictional) |
| **Assessed against** | GDPR (primary reference), ISO/IEC 27701 (management system), EU AI Act (employment and customer-facing AI) |
| **Evidence base** | Enterprise Risk Register v1.0 only (risks R-008, R-010, R-039 to R-046, R-064, R-066, R-073 to R-075) |
| **Prepared** | 2026-10-19 |
| **Owner** | Data Protection Officer |
| **Version** | 0.1 DRAFT |

> **Important limitation.** This is a **desk-based gap assessment built from the risk register alone**. No policies, records of processing, contracts or system configurations were reviewed. Where the register does not mention a requirement, it is marked **"Not evidenced"**. That means the register gives no evidence either way. It does not mean the control is missing. Findings must be validated through interviews and document review before they are reported as compliance conclusions. The register also names 9 operating countries without listing them, so the assessment uses GDPR as the reference model. Local laws in other jurisdictions need a separate check.

---

## 1. Summary

| Result | Count | Meaning |
|---|---|---|
| **Gap** | 4 | Register shows a control is weak or missing |
| **Partial** | 8 | Control exists but is incomplete or untested |
| **Largely in place** | 1 | Control reported as working |
| **Not evidenced** | 5 | Requirement not covered by the register; needs validation |
| **Total requirements assessed** | 18 | |

**Headline findings**

1. **Retention and data minimisation are the weakest area.** R-042 (poor classification and over-retention) has *Weak* controls, a manual labelling process and only a *draft* retention schedule. This enlarges the impact of any breach (GDPR Art. 5(1)(c), 5(1)(e)).
2. **Breach readiness is partly built, but has not been shown to work in 72 hours.** A notification procedure exists, but pre-drafted templates and a 72-hour clock in the IR playbook are still open actions (R-064, due 2026-12-31).
3. **Records and impact assessments are in place, but ageing.** A record of processing activities (ROPA) and DPIAs exist, and the ROPA needs a refresh (R-039). The register tracks overdue DPIAs as a KRI.
4. **International transfers are only partly covered.** Standard contractual clauses (SCCs) and transfer impact assessments exist for the main vendors only; data-flow mapping is incomplete (R-043).
5. **Processor management has contractual gaps.** Legacy supplier contracts lack breach-notification and audit terms (R-073, *Weak*), and subcontractor visibility is limited (R-074, *Weak*).
6. **AI creates new privacy exposure.** Staff can paste personal or confidential data into external AI tools (R-008), and the AI governance for automated CV screening and chatbots is *Weak* (R-010).
7. **Two controls are strong:** full-disk encryption on laptops and USB blocking (R-040 closed, *Strong*).

---

## 2. Gap assessment by requirement

**Rating key:** ✅ Largely in place | 🟡 Partial | 🔴 Gap | ⚪ Not evidenced

| # | Domain and requirement | GDPR ref. | Evidence from register | Rating | Recommended action | Owner | Target |
|---|---|---|---|---|---|---|---|
| 1 | **Governance:** DPO appointed and independent; accountability for privacy | Art. 24, 37 to 39 | DPO owns R-039, so the role exists. Independence, reporting line and resourcing not described | ⚪ | Confirm DPO position, reporting line to the Executive Committee and budget; document in the privacy governance charter | DPO | Q1 2027 |
| 2 | **Records of processing (ROPA)** | Art. 30 | ROPA exists but needs a refresh (R-039) | 🟡 | Refresh the ROPA for CRM, HR and loyalty platforms; assign process owners; review every 6 months | Privacy Analyst | 2027-03-31 |
| 3 | **Lawful basis and consent management** | Art. 6, 7 | Not mentioned | ⚪ | Validate lawful basis per processing activity in the ROPA; review loyalty-programme consent and marketing preferences | Privacy Counsel | Q1 2027 |
| 4 | **Transparency:** privacy notices for customers, dealers, employees and applicants | Art. 12 to 14 | Not mentioned | ⚪ | Review notices for accuracy, including automated decision-making and AI use | Privacy Counsel | Q1 2027 |
| 5 | **Data subject rights** (access, erasure, objection, portability) handled within 1 month | Art. 12, 15 to 22 | Not mentioned; poor data classification (R-042) would slow searching | ⚪ | Test the DSAR process end to end; log volumes and response times as a KRI | DPO | Q1 2027 |
| 6 | **Privacy by design; DPIAs** for new high-risk processing | Art. 25, 35 | DPIAs exist for new processing; "overdue DPIAs" is a KRI (R-039) | 🟡 | Clear the overdue DPIAs; require a DPIA at project gate for any AI use case using personal data | Privacy Analyst | 2027-03-31 |
| 7 | **Data minimisation, classification and retention** | Art. 5(1)(c), 5(1)(e) | Weak controls; manual labelling; retention schedule only drafted; data kept on file shares, SharePoint and email archives (R-042) | 🔴 | Approve the retention schedule; deploy auto-labelling; enforce deletion on file shares; report TB of data past retention | Records Manager | 2027-06-30 |
| 8 | **Security of processing:** encryption, access control, resilience | Art. 32 | Encryption at rest exists. Field-level encryption for HR and loyalty data is planned (R-039). Laptops and USB: strong (R-040). Access weaknesses exist (R-025, R-029) | 🟡 | Implement field-level encryption; complete automated leaver deprovisioning; apply the Access Control Policy | Privacy Analyst; IAM Engineering Lead | 2027-03-31 |
| 9 | **Device and media protection** | Art. 32 | Full-disk encryption on all corporate laptops, USB blocked by default, MDM; closed, Strong (R-040) | ✅ | Monitor encryption compliance quarterly (KRI: % devices encrypted) | Endpoint Engineer | Ongoing |
| 10 | **Insider and leaver data exfiltration** | Art. 32 | DLP on email and web, with extension to cloud storage and user behaviour analytics planned (R-041, R-044) | 🟡 | Deploy UBA; extend DLP to cloud storage; restrict bulk downloads from R&D repositories | Head of Security Operations | 2027-02-28 |
| 11 | **Accidental disclosure** (misdirected email, open sharing links) | Art. 32, 33 | Awareness training, external recipient warnings and partial link expiry in place; DLP policies for external sharing planned (R-046) | 🟡 | Enable DLP rules for external sharing; default links to internal-only | Collaboration Platform Lead | 2026-12-15 |
| 12 | **Personal data breach notification:** regulator within 72 hours; individuals when high risk | Art. 33, 34 | Procedure, legal on call and regulator contact list exist. Templates per jurisdiction and 72-hour clock in playbook still to be added (R-064) | 🟡 | Draft templates for every operating country; embed the clock in the IR playbook; test through the annual notification drill | Privacy Counsel | 2026-12-31 |
| 13 | **Breach detection and logging** | Art. 32, 33 | Logging gaps and business-hours-only monitoring (R-057, Weak); backup recovery is Weak (R-045) | 🔴 | Onboard cloud and SaaS logs; add 24×7 MDR; quarterly restore tests | Head of Security Operations; Infrastructure Lead | 2026-12-31 to 2027-06-30 |
| 14 | **International transfers:** valid transfer mechanism and risk assessment | Art. 44 to 49 | SCCs and transfer impact assessments for main vendors only; data flows not fully mapped (R-043) | 🟡 | Map data flows; complete assessments for all vendors; keep a transfer register linked to the ROPA | Privacy Counsel | 2027-01-31 |
| 15 | **Processor and vendor management:** contracts under Art. 28, audit rights, sub-processors | Art. 28, 32 | Critical vendor risk assessments, breach clauses and annual SOC 2 reviews exist, but Tier-2 vendors are not covered (R-066). Legacy contracts lack security terms (R-073, Weak). Subcontractor visibility is limited (R-074, Weak) | 🔴 | Update the top 50 legacy contracts at renewal with 48-hour breach notification and audit rights; require subcontractor lists and flow-down terms | Commercial Legal Lead; Vendor Risk Manager | 2027-02-28 to 2027-06-30 |
| 16 | **AI and generative tools:** no personal or confidential data in unapproved tools | Art. 5, 32 | AI acceptable use policy, approved enterprise AI tool with no-training terms, partial DLP; DLP rules for external AI and mandatory training planned (R-008) | 🟡 | Deploy DLP for external AI services; publish an AI tool register; complete staff training | Head of Data Governance | 2027-01-15 |
| 17 | **Automated decision-making and AI in HR and customer service** | Art. 22; EU AI Act (high-risk employment use) | Use-case intake form and partial legal review. Controls Weak. Plan: pause the CV screening pilot, then bias-test (R-010) | 🔴 | Keep the pilot paused until bias testing and vendor conformity evidence are available; classify every AI use case by risk; add human review | AI Governance Lead | 2027-02-28 |
| 18 | **Training and awareness** | Art. 39 | General awareness training exists (R-046); privacy-specific training not described | ⚪ | Add role-based privacy training for HR, marketing, customer service and developers | DPO | Q2 2027 |

Rating totals: ✅ 1 | 🟡 8 | 🔴 4 | ⚪ 5 (18 requirements).

---

## 3. Prioritised remediation roadmap

| Priority | Theme | Actions | Rows | Timing |
|---|---|---|---|---|
| **1** | Be able to notify on time and detect a breach | Jurisdiction templates and 72-hour clock in the IR playbook; 24×7 monitoring; cloud and SaaS log onboarding; quarterly restore tests | 12, 13 | By 2026-12-31 |
| **2** | Stop AI-related privacy exposure | DLP for external AI services; AI tool register; keep the CV-screening pilot paused; AI use-case risk classification | 16, 17 | By 2027-02-28 |
| **3** | Close processor and transfer gaps | Complete transfer impact assessments; map data flows; legacy contract updates; subcontractor lists | 14, 15 | By 2027-06-30 |
| **4** | Shrink the data estate | Approve retention schedule; auto-labelling; deletion on file shares; field-level encryption for HR and loyalty data | 7, 8 | By 2027-06-30 |
| **5** | Validate the "not evidenced" areas | Interviews and document review for governance, lawful basis, transparency, DSAR handling and training | 1, 3, 4, 5, 18 | Q1 2027 (start now) |
| **6** | Sustain | Annual ROPA and DPIA review; quarterly KRI reporting; internal audit of privacy controls | 2, 6, 9 to 11 | Ongoing |

Priorities 1 and 2 come first because they address the failures with the shortest time to harm: a missed 72-hour deadline, or personal data leaving the company through AI tools.

## 4. Linked register risks and KRIs

| Risk | Title | Residual | Controls | Privacy KRI in register |
|---|---|---|---|---|
| R-039 | Personal data breach affecting customers or employees | 8 | Adequate | Personal data incidents per quarter; overdue DPIAs |
| R-040 | Unencrypted data on laptops and removable media (closed) | 2 | Strong | % devices encrypted |
| R-041 | Malicious insider exfiltrates sensitive data | 6 | Adequate | High-risk DLP alerts; UBA anomalies investigated |
| R-042 | Poor data classification and over-retention | 9 | Weak | % repositories labelled; data past retention (TB) |
| R-043 | Non-compliant cross-border transfers | 6 | Adequate | % vendors with completed transfer assessment |
| R-044 | Departing employees take trade secrets | 6 | Adequate | Bulk downloads by leavers; NDAs signed |
| R-046 | Misdirected emails and over-shared links | 8 | Adequate | External share incidents; % links with expiry |
| R-064 | Failure to meet breach notification deadlines | 6 | Adequate | Time to regulatory decision in exercises; templates maintained |
| R-008 | Data leakage through generative AI tools | 9 | Adequate | DLP events to unapproved AI services; % staff trained |
| R-010 | Biased or non-compliant AI in hiring and customer service | 9 | Weak | % AI use cases risk-classified; bias test pass rate |
| R-066 / R-073 / R-074 | Vendor breach, weak contract clauses, fourth-party exposure | 9 / 6 / 6 | Adequate / Weak / Weak | % critical vendors with current assessment; % critical contracts with security schedule; % critical vendors with subcontractor map |

**Reading note.** R-042, R-010, R-073 and R-074 carry *Weak* controls but a residual score within appetite. These are the first candidates for a challenge, because a weak control environment makes a Medium residual score optimistic.

## 5. How to validate this assessment

1. Request the ROPA, the retention schedule draft, DPIA register, DSAR log, transfer impact assessments, the breach procedure and 3 sample processor contracts.
2. Interview the DPO, Privacy Counsel, HR (applicant data), Marketing (loyalty data) and the AI Governance Lead.
3. Sample test: one DSAR end to end; one DPIA against the template; one vendor against Art. 28 clauses.
4. Re-rate each row (Compliant, Partial, Gap) using evidence and replace every "Not evidenced" rating.
5. Feed confirmed gaps back into the risk register and update the Annex A mapping (A.5.34 and linked controls).

## 6. Document control

| Version | Date | Author | Description |
|---|---|---|---|
| 0.1 | 2026-10-19 | GRC analyst | Desk-based gap assessment from Risk Register v1.0 |

| Review | Name | Date |
|---|---|---|
| Data Protection Officer | | |
| General Counsel | | |
