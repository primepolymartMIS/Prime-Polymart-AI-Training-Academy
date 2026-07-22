# SOP-009: Company_Name Management

**Document owner:** Prime MIS
**Applies to:** New MIS joinee
**File:** "Master_Sheet for all" → **Company_Name** tab

---

## 1. Purpose

This sheet is the **master reference list of every company/customer name** used across the system. It standardizes company names so that dropdowns in Sale_Form, O2D, D2C, Purchase_Form, etc. all pull from one consistent list — preventing the same company being entered under slightly different spellings in different sheets.

---

## 2. Column Reference

| Column | What it captures |
|---|---|
| COMPANY_Old Name | The company's original/previous recorded name (as it may have first appeared in old records) |
| COMPANY_New Name | The current, standardized name to be used going forward across all sheets |
| MAIL ID | Company's email address |
| PHONE NO. | Company's contact number |
| Unique ID | Auto-generated ID for the company (same PPPL-series ID pattern used in Sale_Form/O2D) |

---

## 3. Why Both an "Old Name" and "New Name" Column Exist

Company names sometimes get entered inconsistently over time (e.g. abbreviations, suffixes like "(K)", "(VJ)", "#", spelling variations, or a company legally renaming itself). To keep reporting accurate:

- **COMPANY_Old Name** preserves the original name as it may have appeared historically, so past order records still match.
- **COMPANY_New Name** is the **corrected/standardized name** that should be used in all new entries and dropdowns going forward.

> 📌 If Old Name and New Name are identical for a row, it simply means no correction was needed for that company.

---

## 4. What a New Joinee Should Do

1. Before creating a new company entry in Sale_Form/O2D/D2C, **search this list first** to check if the company already exists (even under a slightly different old name) — avoid creating a duplicate.
2. If a company's name needs correcting, update **COMPANY_New Name** here rather than editing it individually across other sheets.
3. Keep **MAIL ID** and **PHONE NO.** current — these are pulled into automated communications (invoice emails, WhatsApp reminders) referenced in O2D/D2C SOPs.
4. Never delete a row here even if a customer becomes inactive — historical orders still reference these Unique IDs.

---

*End of SOP-009*
