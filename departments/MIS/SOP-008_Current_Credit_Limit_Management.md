# SOP-008: Current Credit Limit Management

**Document owner:** Prime MIS
**Applies to:** New MIS joinee
**File:** "Master_Sheet for all" → **Current Credit Limit** tab

---

## 1. Purpose

This sheet is the **single source of truth for each customer's current approved credit limit** — it's the value that O2D's "Increase Credit Limit" step (SOP-004, Step 1) and D2C's credit-hold/reopen steps (SOP-007, Steps 3 & 8) both reference.

The data itself isn't entered here manually — it's **pulled in from a separate "CL FMS" (Credit Limit FMS) spreadsheet** using a formula, and then this sheet calculates the **final, usable credit limit** for each customer.

---

## 2. Where the Data Comes From

The columns are populated using an `IMPORTRANGE` + `QUERY` formula pulling from the external **CL FMS** sheet:

```
=QUERY(IMPORTRANGE("https://docs.google.com/spreadsheets/d/.../edit?gid=...","CL FMS!A8:Z"),
"Select Col1,Col12,Col13,Col14,Col15,Col22")
```

This pulls in 6 specific columns from the source CL FMS sheet (Timestamp, Customer Name, Sale Person, Existing limit, New limit, Status_3) — so if a column looks "missing" or in an unexpected order here, check the CL FMS source sheet's column layout first, not this sheet.

> ⚠️ Because this is an IMPORTRANGE-based formula, if the source CL FMS file's sharing access changes, or its `gid` (tab ID) changes, this Current Credit Limit sheet will break/go blank. If that happens, re-check the `IMPORTRANGE` URL and gid in the formula bar (cell A147 in this case).

---

## 3. Column Reference

| Column | What it shows |
|---|---|
| Timestamp | When this credit limit record was logged in CL FMS |
| Customer Name | The customer this limit applies to |
| Sale Person | The SE (Sales Executive) handling this account |
| Existing limit | The customer's previous/current approved limit |
| New limit | A newly requested/updated limit for this customer |
| Status_3 | Whether the new limit is **Permanent** or **Temporary** |
| **Limit In Tally** | The **final calculated limit** to actually use/reflect in Tally (see formula below) |

---

## 4. The "Limit In Tally" Formula

```
=ArrayFormula(IF(F147:F="Permanent", E147:E, D147:D))
```

**In plain terms:**
- If **Status_3 = "Permanent"** → use the **New limit** (column E) as the final limit.
- If **Status_3 = "Temporary"** (or anything else) → fall back to the **Existing limit** (column D) as the final limit.

**Why this matters:** A "Temporary" limit increase (e.g. for a one-off large order) is **not** treated as the customer's real ongoing credit limit. Only once a limit change is marked **Permanent** does it become the standing "Limit In Tally" value that O2D and D2C reference for that customer going forward.

---

## 5. What a New Joinee Should Do

1. Never edit the **Limit In Tally** column manually — it's a formula-driven ArrayFormula and should auto-fill for every new row pulled from CL FMS.
2. If a customer's credit limit looks wrong in O2D/D2C, check this sheet first:
   - Confirm their **Status_3** — a Temporary status means their limit will revert to the old "Existing limit" once you check Limit In Tally.
   - Cross-check against the source **CL FMS** sheet if the numbers don't match what's expected.
3. Use this sheet as your reference whenever O2D Step 1 ("Increase Credit Limit") needs verification of what the customer's actual usable limit is.

---

*End of SOP-008*
