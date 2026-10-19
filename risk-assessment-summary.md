# Risk Assessment Summary

**Organisation:** Meridian Provisions Group (fictional) | **Source:** Enterprise Risk Register v1.0 (prepared 2026-10-14) | **Summary date:** 2026-10-19
**Methodology:** ISO 31000, 5×5 likelihood × impact matrix | **Appetite:** residual score ≤ 9 (Medium or lower)

---

## 1. Executive summary

The register holds **75 risks** across 13 categories. Before controls, **61 (81%) are High or Critical**; after controls, **12 (16%)** remain High or Critical. Existing controls reduce the average score from **12.6 to 7.7 (−39%)**, and **84% of residual risks are within appetite**.

The residual exposure is concentrated in **cyber security**. Of the 12 risks outside appetite, **10 are cyber risks**, and the only residual *Critical* risk is **R-061 Ransomware on corporate IT (score 15)**. Nine of the 12 have *Weak* control effectiveness, so the gap lies in controls that are not working, not in risks that are inherently unmanageable.

**Five messages for leadership**

1. **Ransomware is the dominant exposure, on both the IT and OT sides.** R-061 (15), R-012 (12) and R-045 (12) form one scenario chain: initial access, then spread, then failed recovery. They should be funded and tracked as a single programme.
2. **Recoverability is the weakest link.** Backups are untested (R-045, Weak) and R-061 relies on "offline backups (not fully tested)". Immutable backups and quarterly restore tests are the highest-value fixes.
3. **OT security is behind IT security.** Three OT risks are outside appetite (R-012, R-068, R-069). Segmentation covers 9 of 14 plants, and R-069 (legacy PLC/SCADA) has a target date of March 2028.
4. **Vulnerability and asset hygiene is slipping.** R-031 (unpatched internet-facing systems) and R-033 (end-of-life systems) are Weak and High. R-031's action is already past its target date.
5. **Four mitigation actions are overdue** (section 6). Two of them, R-031 and R-050, are cyber risks with Weak controls.

---

## 2. Rating distribution

| Rating | Inherent | Residual |
|---|---|---|
| Critical (15–25) | 25 | 1 |
| High (10–14) | 36 | 11 |
| Medium (5–9) | 14 | 57 |
| Low (1–4) | 0 | 6 |
| **Total** | **75** | **75** |

Treatment mix: Mitigate 66, Accept 4, Transfer 3, Avoid 2. Status: Open 32, In Progress 35, Monitoring 6, Closed 2.

---

## 3. Risks outside appetite (residual > 9)

| ID | Risk | Inherent → Residual | Controls | Owner | Target | Status |
|---|---|---|---|---|---|---|
| R-061 | Ransomware attack on corporate IT systems | 20 → 15 | Weak | Chief Information Security Officer | 2027-03-31 | In Progress |
| R-012 | Ransomware targeting plant operational technology (OT) | 20 → 12 | Weak | Chief Information Security Officer | 2027-06-30 | In Progress |
| R-031 | Unpatched vulnerabilities on internet-facing systems | 16 → 12 | Weak | Head of IT Operations | 2026-09-30 | In Progress |
| R-033 | End-of-life operating systems and software in production | 16 → 12 | Weak | Chief Information Officer | 2027-03-31 | In Progress |
| R-049 | Vulnerable open-source dependencies and software supply chain | 16 → 12 | Weak | Head of Engineering | 2027-04-30 | Open |
| R-068 | Insecure remote access by OT vendors to plant systems | 16 → 12 | Weak | Head of OT Security | 2027-02-28 | In Progress |
| R-069 | Legacy PLC and SCADA systems with no patch path | 16 → 12 | Weak | Chief Operating Officer | 2028-03-31 | Open |
| R-002 | Flooding and storm damage at coastal plants | 15 → 12 | Adequate | Chief Operating Officer | 2027-06-30 | Open |
| R-004 | Single-source dependency for specialty packaging film | 15 → 12 | Weak | Chief Procurement Officer | 2026-09-30 | In Progress |
| R-032 | Zero-day exploitation of VPN and edge appliances | 15 → 12 | Adequate | Chief Information Security Officer | 2027-06-30 | In Progress |
| R-045 | Backup failure or inability to restore after an attack | 15 → 12 | Weak | Head of IT Operations | 2026-12-31 | In Progress |
| R-067 | Compromise of a managed service provider | 15 → 12 | Adequate | Chief Information Security Officer | 2027-03-31 | Open |

**Observations**

- Eleven of the 12 have a residual impact of 4 or 5 (Major or Severe); R-069 is the exception, with residual impact 3 but likelihood 4. Controls have reduced likelihood to 3 for most of them but have not changed what a successful attack would do, so **resilience and recovery controls** (segmentation, immutable backups, manual-mode operations) matter more than additional prevention.
- All 12 have a treatment plan and an owner, which satisfies the "High" required response on the Scoring sheet. R-061 is Critical, so it needs **executive or risk-committee escalation and a 30-day review cycle**.
- R-002 (flood damage) and R-004 (single-source film) are the only two non-cyber items.

---

## 4. Category view

| Category | Risks | Avg inherent | Avg residual | Reduction | Outside appetite |
|---|---|---|---|---|---|
| Climate & Environment | 2 | 15.5 | 10.5 | 32% | 1 |
| Supply Chain & Logistics | 3 | 14.3 | 10.0 | 30% | 1 |
| Financial & Market | 2 | 14.0 | 9.0 | 36% | 0 |
| Cyber: Network & Infrastructure | 8 | 12.2 | 8.4 | 32% | 3 |
| Cyber: OT & Third-Party | 11 | 12.8 | 8.3 | 35% | 4 |
| Technology & AI | 3 | 13.3 | 8.0 | 40% | 0 |
| Regulatory & ESG | 3 | 12.0 | 7.7 | 36% | 0 |
| Cyber: Threat & Incident Response | 9 | 12.3 | 7.4 | 40% | 1 |
| Cyber: Data Protection & Privacy | 8 | 12.1 | 7.1 | 41% | 1 |
| Cyber: Identity & Access | 10 | 12.7 | 7.0 | 45% | 0 |
| Cyber: Application & Cloud | 10 | 13.2 | 7.0 | 47% | 1 |
| Operational Resilience | 2 | 9.0 | 7.0 | 22% | 0 |
| Workforce & Operating Model | 4 | 11.2 | 6.8 | 40% | 0 |

Climate & Environment and Supply Chain carry the highest average residual scores but have few risks. The cyber sub-categories hold **56 of the 75 risks** (average residual 7.5). Network & Infrastructure has the weakest control reduction among the cyber sub-categories.

---

## 5. Control effectiveness

| Effectiveness | Risks | Avg residual score | Within appetite |
|---|---|---|---|
| Strong | 4 | 3.5 | 4 of 4 |
| Adequate | 49 | 7.3 | 46 of 49 |
| Weak | 22 | 9.4 | 13 of 22 |

- **22 of 75 risks (29%) rely on Weak controls**; 19 of those are cyber risks. Weak controls leave residual scores about 2 points higher than Adequate ones.
- The recurring weakness pattern is **partial rollout**: segmentation at 9 of 14 plants, EDR not at 100%, opt-in secret scanning, NAC at HQ only, an incomplete service-account register, and annual firewall reviews that were not completed. These are implementation gaps with clear fixes, not design failures.
- Thirteen risks with Weak controls are still scored within appetite (≤ 9). Weak controls combined with a Medium residual score deserve a second look, so these should be **challenged at the next review**: R-010, R-015, R-025, R-027, R-029, R-036, R-042, R-050, R-057, R-065, R-070, R-073 and R-074.

---

## 6. Overdue actions (target date before 2026-10-19, not closed)

| ID | Risk | Action owner | Target date | Status |
|---|---|---|---|---|
| R-004 | Single-source dependency for specialty packaging film | Packaging Category Manager | 2026-09-30 | In Progress |
| R-009 | AI demand forecast drift causes inventory errors | ML Engineering Lead | 2026-10-10 | In Progress |
| R-031 | Unpatched vulnerabilities on internet-facing systems | Infrastructure Lead | 2026-09-30 | In Progress |
| R-050 | Secrets and API keys hardcoded in code repositories | DevSecOps Lead | 2026-10-10 | In Progress |

The dashboard reports **4** open actions past target, which matches this list. Owners should either re-baseline the dates with a documented reason or report recovery plans at the next risk committee. R-031 and R-004 are both outside appetite, so their slippage matters most.

---

## 7. Recommended treatment priorities

| Priority | Action | Linked risks | Suggested horizon |
|---|---|---|---|
| 1 | Immutable backups, quarterly restore tests, EDR to 100%, ransomware tabletop, IR and forensics retainer | R-061, R-045, R-058 | Q4 2026 – Q1 2027 |
| 2 | Recover overdue patching: critical vulnerabilities within 7 days, weekly external scans | R-031, R-032 | Immediate |
| 3 | Complete IT/OT segmentation (remaining 5 plants), OT asset inventory, centralised vendor access via OT jump server | R-012, R-068 | Q1 – Q2 2027 |
| 4 | Retire or isolate end-of-life systems with compensating controls | R-033 | Q1 2027 |
| 5 | Software supply chain: SBOMs, signed builds, org-wide secret scanning | R-049, R-050 | Q1 – Q2 2027 |
| 6 | MSP access: just-in-time with session recording, right-to-audit clauses | R-067, R-066, R-073, R-074 | Q1 2027 |
| 7 | Plan OT lifecycle replacement and virtual patching; agree interim risk acceptance with the Board | R-069 | Plan by Q1 2027 |
| 8 | Non-cyber: second packaging supplier; flood barriers and insurance sublimit review | R-004, R-002 | Per register dates |

---

## 8. Register data-quality notes

- **Naming mismatch:** the README header says "Northwind Financial Group", while the rest of the workbook says Meridian Provisions Group. This summary uses Meridian, as the company profile does.
- **Arithmetic:** every inherent and residual score equals likelihood × impact, and the ratings are consistent with the bands (0 mismatches).
- **Accepted risks (R-022, R-038, R-053, R-072)** have no target date, which is appropriate, but each needs a documented acceptance sign-off and an annual re-test.
- **Closed risks (R-040, R-055)** carry residual scores of 2 and are scheduled for a 365-day review, which is consistent with the Scoring sheet.
- Dollar thresholds on the Scoring sheet are illustrative and need calibrating against real financials before the scores are used for decisions.

---

## 9. Linked deliverables

- `../02-iso27001/isms-scope.md` and `../02-iso27001/annex-a-control-mapping.xlsx` map these risks to ISO 27001:2022 Annex A.
- `../03-policies/` contains the access control and incident response policies, which implement the treatment actions for the Identity & Access and Threat & Incident Response categories.
- `../04-privacy/privacy-gap-assessment.md` covers the Data Protection & Privacy risks (R-039 to R-046, R-064).
