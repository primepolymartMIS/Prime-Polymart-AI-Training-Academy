# SOP-006: Purchase_FMS Management

**Document owner:** Prime MIS
**Applies to:** New MIS joinee
**File:** "Master_Sheet for all" → **Purchase_FMS** tab

---

## 1. Purpose

Once a purchase order is captured on **Purchase_Form** (see SOP-005), it moves into the **Purchase_FMS** sheet, where it is tracked through **4 fulfillment steps** — from updating the PO in Tally to taking the final purchase entry. This is the buy-side equivalent of the O2D sheet (SOP-004).

---

## 2. Where Purchase_FMS Data Comes From

The first columns of Purchase_FMS are the **same PO details captured on Purchase_Form** (Timestamp, PO No., Agent Name, Company Name, Product, Quantity, Rate, Send PO to company, Self Pickup/delivery by vendor, Date and time of pickup/delivery). A blank spacer column follows, then the step-tracking columns begin.

---

## 3. The 5-Part Step Structure (same pattern as O2D)

Each step is tracked using: **Planned, Actual, Status, Delay, Done By** — same meaning as described in SOP-004:

| Field | Meaning |
|---|---|
| **Planned** | Time limit set for the task to be completed |
| **Actual** | Time the doer actually completed it |
| **Status** | Done / Not Done |
| **Delay** | How much time late vs. Planned |
| **Done By** | Email ID of the doer who completed it |

> 📌 **Note:** Step 3 in this sheet does **not** have a Delay column (it only has Planned, Actual, Status, Done By) — this is a slight structural difference from the other steps, so don't be confused if it looks shorter when reviewing that step.

---

## 4. The 4 Fulfillment Steps

### Step 1 — Update PO in Tally
- **Who:** CRM
- **What:** CRM checks the purchase order and updates it in Tally.

### Step 2 — Send Official PO to Company / Update PO in Company Portal
- **Who:** Accounts
- **What:** The Accounts person checks the PO and shares it on the vendor's portal (or sends the official PO document to the company).

### Step 3 — Material Receive
- **Who:** Logistics
- **What:** Logistics checks whether the ordered material has actually been received — whether it was **self-pickup** or **delivery by vendor**, per the Purchase_Form entry.
- *(No Delay column tracked for this step — see note above.)*

### Step 4 — Take Purchase Entry in Tally
- **Who:** Accounts
- **What:** The Accounts person does a final check and records the purchase entry in Tally, closing out the PO.

---

## 5. Trailing Columns

| Column | Purpose |
|---|---|
| Doer E-Mail | Email used for AppSheet notifications/automation routing |
| Unique Id | Auto-generated ID matching back to the Purchase_Form row |

---

## 6. Quick Reference — All 4 Steps at a Glance

| Step | Task | Owner | Notes |
|---|---|---|---|
| 1 | Update PO in Tally | CRM | — |
| 2 | Send Official PO / update vendor portal | Accounts | — |
| 3 | Material Receive | Logistics | Checks Self Pickup vs. Delivery by Vendor; no Delay tracked |
| 4 | Take Purchase Entry in Tally | Accounts | Final closing entry |

---

## 7. What a New Joinee Should Do

1. Open **Purchase_FMS**, pick any PO row, and scroll across the 4 steps to see where it currently stands.
2. If **Status** shows Not Done and **Delay** is high (where tracked), flag it to the responsible department (CRM/Accounts/Logistics per the table above).
3. Cross-check that **Step 3 (Material Receive)** matches what was promised in Purchase_Form (Self Pickup / delivery by vendor) before closing the PO.

---

*End of SOP-006*
