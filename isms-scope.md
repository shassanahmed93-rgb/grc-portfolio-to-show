# ISMS Scope Statement

| | |
|---|---|
| **Organisation** | Meridian Provisions Group (fictional) |
| **Standard** | ISO/IEC 27001:2022, clauses 4.1 to 4.3 |
| **Document owner** | Chief Information Security Officer (CISO) |
| **Approver** | Executive Committee / Risk Committee |
| **Version** | 0.1 DRAFT |
| **Date** | 2026-10-19 |
| **Review cycle** | Annually, or on a material change to the business, sites or technology |

> **Status.** This is a draft prepared from the Enterprise Risk Register v1.0. Items marked **[Assumption]** are proposals that management must confirm. They are not facts taken from the register.

---

## 1. Purpose

This document defines the boundaries and applicability of the Information Security Management System (ISMS) at Meridian Provisions Group, as required by ISO/IEC 27001:2022 clause 4.3. It states what is inside the ISMS, what is outside it, and why.

## 2. Organisational context (clause 4.1)

Meridian is a global packaged-food manufacturer with about 6,200 employees, 14 plants in 9 countries and annual revenue of about $2.4B. About 2,500 staff work in hybrid or remote arrangements.

Four forces shape the information security risk profile, as described in the risk register:

| Driver | Security consequence | Example register risks |
|---|---|---|
| **AI adoption** (forecasting, plant analytics, customer service) | Data leakage to AI tools; connecting plant systems to analytics widens the attack surface; AI governance and privacy exposure | R-008, R-010, R-012 |
| **Hybrid work** | Phishing and credential theft, unmanaged devices, session-token theft | R-013, R-014, R-030 |
| **Operational technology and plant connectivity** | Ransomware and vendor access reaching production; legacy control systems with no patch path | R-012, R-068, R-069 |
| **Supply chain and third parties** | Vendor and MSP compromise, weak contract clauses, fourth-party exposure | R-066, R-067, R-073, R-074 |

The register contains 75 risks, of which 56 are cyber security risks. 12 risks remain outside appetite after controls, and 10 of those are cyber risks. The scope below is drawn so that every one of those 10 falls inside the ISMS.

## 3. Interested parties and their requirements (clause 4.2)

| Interested party | Relevant requirements |
|---|---|
| Customers, dealers and consumers | Protection of personal and order data; availability of the ordering portal |
| Employees and contractors | Lawful handling of HR data; clear acceptable-use rules |
| Regulators and data protection authorities | GDPR and equivalent privacy laws (including the 72-hour breach notification duty); AI regulation such as the EU AI Act; import and due-diligence laws |
| Board, investors and lenders | Credible risk governance; climate and sustainability disclosure |
| Insurers | Completed security questionnaires; alignment of policy limits to modelled loss (R-075) |
| Suppliers, MSPs and OT vendors | Clear access rules and contractual security terms |
| Retail customers and auditors | Evidence of control, for example ISO 27001 certification or SOC 2 reports **[Assumption]** |

## 4. Scope of the ISMS (clause 4.3)

### 4.1 Scope statement

> The ISMS of Meridian Provisions Group covers the confidentiality, integrity and availability of information, and of the information systems and operational technology that process it, used to design, source, manufacture, sell and distribute packaged food products, across all corporate functions and all 14 manufacturing plants. It is applied to the people, processes, technology, suppliers and locations described below.

### 4.2 In scope

| Area | Included items | Register risks it treats |
|---|---|---|
| **Corporate IT** | Endpoints (corporate laptops, MDM-managed devices, BYOD access), identity systems (Active Directory, Entra ID), Microsoft 365 tenant, file shares, SharePoint | R-013, R-014, R-023 to R-030, R-054 |
| **Business applications** | ERP and finance systems, CRM, HR system, loyalty database, demand-planning and AI forecasting platforms | R-009, R-026, R-039 |
| **Customer-facing digital services** | Dealer and customer ordering portal, public website, public and partner APIs | R-028, R-035, R-051 |
| **Cloud and engineering** | Primary cloud region and accounts, containers and Kubernetes, CI/CD pipelines, source repositories | R-047 to R-052, R-056, R-071 |
| **Network and infrastructure** | Data centre, perimeter and internal firewalls, VPN and edge appliances, DNS and domains, Wi-Fi, backup platform | R-031 to R-038, R-045 |
| **Operational technology (security governance)** | OT networks, PLC, SCADA, HMIs, industrial IoT, vendor remote access, at all 14 plants. IEC 62443 provides the technical control baseline and the ISMS governs it | R-012, R-068, R-069, R-070 |
| **Security operations** | SIEM, EDR, SOC, threat intelligence, incident response, breach notification | R-057 to R-065 |
| **Information** | Customer, dealer and employee personal data; recipes, formulations and R&D data; supplier pricing and contracts; financial data; strategic plans | R-039 to R-044, R-062 |
| **People** | All employees, contractors and temporary staff with access to the above | R-011, R-029, R-044, R-060 |
| **Third parties** | Managed service providers, payroll, logistics and marketing vendors, OT vendors, cloud providers, subcontractors | R-066, R-067, R-072 to R-074 |
| **Locations** | Head office, regional offices, 14 plants, data centre, remote and home working | All |

### 4.3 Out of scope and justification

| Excluded item | Justification | Residual treatment |
|---|---|---|
| Food safety, quality and product-safety management systems (for example HACCP and certified food-safety schemes) **[Assumption]** | Governed by separate management systems and regulators; they are not information security controls | Interface managed under 4.4 below |
| Physical operation of production lines, except where it depends on in-scope OT | Process safety and machinery safety are covered by ISO 45001 and plant procedures | OT security governance remains in scope |
| Consumer-owned devices and networks | Outside organisational control | Access is governed by the remote working policy and zero-trust access controls |
| Independent third-party systems that hold no Meridian data and have no connection to in-scope systems | No information flow | Reassess if a connection or data transfer is added |
| Enterprise risks that are not information security risks (climate, tariffs, workforce, energy, currency; R-001 to R-007, R-015 to R-022) | Managed under the enterprise risk process (ISO 31000) | Reported through the same register; relevant continuity risks cross-referenced |

No Annex A control has been excluded from the Statement of Applicability at this stage (see `annex-a-control-mapping.xlsx`).

### 4.4 Interfaces and dependencies

| Interface | Dependency | Control |
|---|---|---|
| Business continuity (ISO 22301) | Recovery objectives for tier-1 applications and plant operations | A.5.29, A.5.30; tested restore and failover (R-045, R-071) |
| Supply chain security (ISO 28000) | Logistics and procurement vendors that connect to Meridian systems | A.5.19 to A.5.22 |
| Privacy management (ISO 27701) | Personal data processing in CRM, HR and loyalty platforms | A.5.34; see `04-privacy/` |
| AI governance (ISO/IEC 42001, NIST AI RMF) | AI use cases that process confidential or personal data | A.5.10, A.8.12; R-008, R-010 |
| OT security (IEC 62443) | Technical OT controls | A.8.20, A.8.22; R-012, R-068, R-069 |
| Cloud and SaaS providers | Shared-responsibility model | A.5.23; R-047, R-071 |

## 5. Phasing recommendation **[Assumption]**

The OT environment is the least mature part of the scope (segmentation at 9 of 14 plants; target date for legacy control-system replacement in 2028). A pragmatic approach is:

1. **Phase 1 (certification scope):** corporate IT, cloud, business applications, customer-facing services, security operations and OT security governance at headquarters.
2. **Phase 2:** extend the formal ISMS audit scope plant by plant as segmentation and asset inventory reach 100% (R-012).

Management could instead certify the full scope at once, but that choice would put the lowest-maturity area directly into the first audit. Whichever option is chosen, **all 14 plants stay inside the risk assessment**, because the risks are real regardless of the certification boundary.

## 6. Leadership, policy and roles (clauses 5.1 to 5.3)

| Role | ISMS responsibility |
|---|---|
| Executive Committee | Approves the scope, policy and risk appetite; provides resources |
| CISO | Owns the ISMS; reports performance to the Risk Committee |
| Chief Information Officer, Chief Digital Officer, COO (for OT) | Own the systems in scope and implement controls |
| Data Protection Officer and General Counsel | Privacy compliance and legal, regulatory and contractual requirements |
| Chief People Officer | Screening, awareness, offboarding, disciplinary process |
| Chief Procurement Officer, Vendor Risk Manager | Supplier assurance and contract security clauses |
| Risk owners (per register) | Accept, treat and monitor each risk and its KRIs |

## 7. Risk assessment link (clauses 6.1 and 8.2)

- Risks are assessed with the ISO 31000-aligned 5×5 method in the register: likelihood × impact, scores from 1 to 25, bands Low (1 to 4), Medium (5 to 9), High (10 to 14), Critical (15 to 25).
- **Risk appetite:** a residual score of 9 or below is acceptable **[Assumption in the register; needs Board approval]**.
- Treatment decisions are recorded in the register and mapped to Annex A in `annex-a-control-mapping.xlsx`, which acts as the working draft of the Statement of Applicability.
- Review frequency follows the residual rating: Critical 30 days, High 90, Medium 180, Low 365.

## 8. Scope boundaries diagram (text)

```
+-----------------------------------------------------------------------+
| ISMS boundary                                                         |
|  People ─ Corporate IT ─ Identity ─ M365 ─ ERP/CRM/HR ─ Data          |
|     │          │                                                      |
|     │      Cloud / CI-CD / Containers ─ Portal / APIs                 |
|     │          │                                                      |
|     │      Network / Edge / Backup ─ SOC / IR                         |
|     │          │                                                      |
|  14 plants: OT network ─ PLC/SCADA ─ IoT ─ vendor access (governed)   |
|                                                                       |
|  Third parties: MSPs ─ payroll/logistics/marketing ─ OT vendors       |
+-----------------------------------------------------------------------+
   Outside: food-safety systems, line machinery safety, consumer devices
   Interfaces: ISO 22301 | ISO 28000 | ISO 27701 | ISO/IEC 42001 | IEC 62443
```

## 9. Approval and document control

| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | 2026-10-19 | GRC analyst | First draft from Risk Register v1.0 |

| Approval | Name | Signature | Date |
|---|---|---|---|
| CISO | | | |
| Chief Risk Officer or CFO | | | |
| Chief Executive Officer | | | |
