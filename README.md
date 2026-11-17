# SOX 404 IT General Controls (ITGC) & Application Controls Workpaper Portfolio

A collection of standardized public accounting audit workpapers demonstrating end-to-end ITGC walkthroughs, Information Produced by the Entity (IPE) completeness validation, Computer-Assisted Audit Techniques (CAATs), and SOX 404 deficiency evaluation across enterprise financial systems (SAP S/4HANA, Workday HRIS, ServiceNow, and GitHub Actions CI/CD).

---

## Portfolio Index

| Workpaper Ref | Control Area | In-Scope Systems | Methodology & Sample Size | Key Exceptions & Conclusion | Files |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **`WP-LA-02-UAR`** | **Logical Access:** Periodic User Access Review & Deprovisioning (`ITGC-LA-02`) | SAP S/4HANA (`SUIM`), Workday HRIS | **100% Population CAATs** (150 ERP accounts reconciled against 140 HR records) | **Ineffective:** Flagged 4 separated employees still active in ERP, active accounts bypassing MFA, dormant accounts (>90 days), and unauthorized non-IT `SuperUser` access. | [Excel](WP_ITGC_LA02_User_Access_Review.xlsx) \| [Memo PDF](WP_ITGC_LA02_User_Access_Review.PDF) |
| **`WP-CM-01-SDLC`** | **Change Management:** SDLC Pipeline & Release Controls (`ITGC-CM-01`) | ServiceNow Change Mgmt, GitHub Actions CI/CD, SAP, Billing, Payroll | **Completeness Reconciliation** (188 CI/CD logs vs. 185 tickets) + **25-Item Attribute Sample** | **Ineffective:** Identified 3 untracked direct-to-prod pushes (`DEP-59901`–`59903`) and 3 sample deviations (pre-approval deployment, self-approved PR, and manual override of failed unit tests). | [Excel](WP_ITGC_CM01_Change_Management_SDLC.xlsx) \| [Memo PDF](WP_ITGC_CM01_Change_Management_SDLC.PDF) |
| **`WP-LA-04-SOD`** | **Application Access:** ERP Segregation of Duties Matrix (`ITGC-LA-04`) | SAP S/4HANA (`USR02`, `AGR_USERS`, `AGR_1251`) | **10×10 Pairwise Conflict Matrix** across 8 toxic T-code pairs tested over 45 active ERP users | **Ineffective:** Flagged 7 users with toxic combinations—1 mitigated via monthly CFO review of JEs >$5,000, and 6 unmitigated deficiencies across P2P, O2C, Payroll, and IT Security. | [Excel](WP_ITGC_LA04_Segregation_of_Duties.xlsx) \| [Memo PDF](WP_ITGC_LA04_Segregation_of_Duties.PDF) |

---

## Workpaper Architecture & Audit Methodology

Every workbook follows a consistent four-tab public accounting documentation standard:

1. **`Audit_Memo`:** Documents control objectives, walkthrough narratives, IPE completeness and accuracy procedures, AICPA/PCAOB sampling rationale, root-cause exception write-ups (Condition, Criteria, Cause, Risk), and operating effectiveness conclusions.
2. **`01_Source_Population / Ruleset`:** Baseline system extracts or audit criteria (Workday census, ServiceNow ticket log, or 10×10 SAP T-code SoD matrix).
3. **`02_Target_Population / Sample`:** Granular ERP user dumps, sampled change tickets, or flattened binary (`Yes`/`No`) user-to-T-code entitlement tables.
4. **`03_Automated_Testing_Schedule`:** Dynamic CAATs schedules utilizing `XLOOKUP`, nested `IF/AND` attribute logic, ISO timestamp sequencing, and `COUNTIF` executive roll-up summaries to eliminate manual ticking-and-tying errors.

---

## Core Technical & Audit Competencies Demonstrated

* **SOX 404 & PCAOB AS 2201 / AICPA AU-C 330:** Risk-based scoping, IPE source validation, attribute sampling vs. 100% population analytics, compensating control evaluation, and linking ITGC deficiencies to substantive year-end audit procedures.
* **ERP & DevOps Environments:** SAP S/4HANA financial transaction codes (`XK01`, `ME21N`, `MIGO`, `MIRO`, `F110`, `FB50`, `FV50`, `VF01`, `F-28`, `PA30`, `PC00`, `PFCG`), ServiceNow Change Management workflows, and GitHub branch protection / CI/CD pipeline segregation (`svc_github_actions`).
* **Audit Analytics (CAATs):** Automated exception flagging, cross-system reconciliation, and dynamic summary reporting designed for direct translation into Alteryx Designer or Python (`pandas`).

---

## Author

**Tran Dang Quang (Thomas) Nguyen**  
* Passed all 4 sections of the Uniform CPA Examination  
* M.A.S. in Computer Science Candidate, University of Pennsylvania | B.S. in Accounting, Western Governors University  
* Certifications: CompTIA Security+, Network+, A+  
