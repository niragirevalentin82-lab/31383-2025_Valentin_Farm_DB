# 31383-2025_Valentin_Farm_DB
Project work 
# README — DPR400210 Capstone Submission
### Farmer Produce & Market Supply Chain Management System
**Student:** Valentin &nbsp;|&nbsp; **Student ID:** 31383/2025 &nbsp;|&nbsp; **Database:** `31383_2025_Valentin_Farm_DB`

This folder contains everything produced for the capstone project. Files are grouped below by submission requirement (Phase VIII, Section 7) with the order you should run/read them in.

---

## 1. SQL Scripts (`/sql`)
Run in this order against your Oracle schema:

| File | Contents |
|---|---|
| `sql/01_schema_and_data.sql` | User/database creation, all 9 tables with PK/FK/CHECK/UNIQUE/NOT NULL constraints, sequences, sample data |
| `sql/02_plsql_programs.sql` | `calc_sale_total` function, `register_farmer` procedure, `farm_pkg` package (spec + body), demo execution block |
| `sql/03_triggers_audit_security.sql` | `trg_sale_business_rule` (weekday/holiday block), `trg_audit_sale`, `trg_audit_payment`, roles/grants, `v_unpaid_sales` view |

## 2. PL/SQL Scripts
Included inside `sql/02_plsql_programs.sql` and `sql/03_triggers_audit_security.sql` above — no separate file, since Oracle PL/SQL and SQL DDL are typically submitted together per script.

## 3. Final Report
| File | Contents |
|---|---|
| `31383_2025_Valentin_Farm_DB_Capstone_Report.docx` | Full write-up: Phase I (Problem Statement) through Phase VIII (APEX + Documentation), including all SQL/PL-SQL code and placeholder boxes for your screenshots |

## 4. Live Demonstration
| File | Contents |
|---|---|
| `Live_Demonstration_Script.md` | Command-by-command walkthrough covering all 6 required demo items (database structure, queries, PL/SQL, triggers/packages, audit system, APEX), with a timing guide |
| `APEX_Build_Checklist.md` | Step-by-step instructions for actually building the APEX app referenced in the demo script |

## 5. Presentation Slides (supplementary)
| File | Contents |
|---|---|
| `Phase_VIII_Final_Presentation.pptx` | 10-slide final presentation deck: Introduction → Problem → Methodology → Database Design → Implementation → Results → Conclusion |
| `Phase_I_Problem_Statement.pptx` | 3-slide deck covering Phase I only |
| `Phase_II_Business_Process_Model.docx` | Phase II workflow diagram + one-page written explanation |
| `workflow.png` | Standalone image of the Phase II swimlane diagram |

---

## Suggested order of use

1. **Set up your database** — run the three scripts in `/sql`, in order.
2. **Build the APEX app** — follow `APEX_Build_Checklist.md` step by step.
3. **Take screenshots** as you go (OEM user creation, SQL execution, trigger tests, audit log, each APEX page) and drop them into the placeholder boxes in the Capstone Report `.docx`.
4. **Rehearse your live demo** using `Live_Demonstration_Script.md` — do at least one full run-through before presenting.
5. **Present** using `Phase_VIII_Final_Presentation.pptx` (or build out the remaining phases into slides if your instructor wants full-phase coverage — ask and they can be added).

---

## Known gaps to close before submission

- All screenshot placeholders in the Word report are still empty — these must come from your own Oracle/APEX session.
- The `app_user_role` mapping table in `APEX_Build_Checklist.md` (Stage 7) is an APEX-only addition for authorization — it's not part of the core schema in `sql/01_schema_and_data.sql`, so add it separately if you implement role-based page access.
- `trg_sale_business_rule` blocks sale inserts on weekdays — remember to disable/re-enable it (commands included in `sql/03_triggers_audit_security.sql`) when loading demo data outside a weekend.
