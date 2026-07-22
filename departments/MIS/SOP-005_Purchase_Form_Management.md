# SOP-005: Purchase_Form Management

**Document owner:** Prime MIS
**Applies to:** New MIS joinee
**File:** "Master_Sheet for all" → **Purhase_Form** tab

---

## 1. Purpose

Just like **Sale_Form** is the entry point for a customer sale order (see SOP-003), **Purchase_Form** is the entry point for a **purchase order (PO)** raised to a vendor/supplier for raw material.

The workflow pattern is the same as the sale side: a form (AppSheet) submission creates a new row here, and this raw data then flows into **Purchase_FMS** for step-by-step tracking (see SOP-006).

---

## 2. Purchase_Form — Column Reference

| # | Column | What it captures |
|---|---|---|
| 1 | Timestamp | Date/time the PO was submitted |
| 2 | PO No. | Purchase order number |
| 3 | Agent Name | Person/agent who placed the purchase |
| 4 | Company Name | Vendor/supplier company |
| 5 | Product | Product/material being purchased |
| 6 | Quantity (in kg only) | Purchase quantity |
| 7 | Rate? (Per Kg in Rupees Only) | Agreed purchase rate |
| 8 | Send PO to company | Whether the PO has been sent to the vendor |
| 9 | Self Pickup / delivery by vendor | Who is responsible for transporting the material |
| 10 | Date and time of pickup / delivery | Scheduled pickup/delivery slot |
| 11 | Remarks | Free-text notes |
| 12 | Unique Id | Auto-generated ID for the PO row |

---

## 3. What a New Joinee Should Do

1. Get familiar with this column list — it mirrors the Sale_Form structure, just from the buying side instead of the selling side.
2. Once a PO is captured here, move to **SOP-006 (Purchase_FMS)** to see how it's tracked through to completion.

---

*End of SOP-005*
