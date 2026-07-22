# SOP-007: D2C (Payment FMS) Management

**Document owner:** Prime MIS
**Applies to:** New MIS joinee
**File:** "Master_Sheet for all" → **D2C** tab

---

## 1. Purpose

While **O2D** (SOP-004) tracks an order from placement through delivery, **D2C (Payment FMS)** takes over **after delivery** — it tracks whether the customer's **payment** for that order is collected on time, and manages the escalation process (credit hold, insurance claim, credit reopen) if it isn't.

Think of it as: **O2D = did we deliver correctly → D2C = did we get paid correctly.**

---

## 2. Where D2C Data Comes From

The base order columns (Time Stamp, Unique Key, Order No, Company Name, S E, Product, Qty, Rate, Credit Note, Delivery Type, Delivery Charges, Unloading Labour, Mtc, P T, Delivery On Date?, Customers/Trader, Pdc, Remarks, Ship To Address) are **the same fields as O2D** — this is the same order, just now viewed from the payment-tracking side.

D2C then adds payment-specific tracking columns before the step columns begin:

| Column | What it shows |
|---|---|
| Overdues Days | How many days the payment is currently overdue |
| Payment Due date | The date payment was due |
| Pending Amount | Amount still outstanding on this order |
| Remark_2 | Additional follow-up note |
| Remarks Date | Date the last remark was added |
| Next Follow UP Date | Date of the next scheduled follow-up call/reminder |

---

## 3. The 5-Part Step Structure (same pattern as O2D)

Each step is tracked using **Planned, Actual, Status, Delay (or Time Delay), Done By** — same meaning as SOP-004:

| Field | Meaning |
|---|---|
| **Planned** | Time limit set for the task |
| **Actual** | Time the doer actually completed it |
| **Status** | Done / Not Done |
| **Delay / Time Delay** | How much time late vs. Planned |
| **Done By** | Email ID of the doer who completed it |

> 📌 Note: Steps 1–3 use the column name **"Delay"**, while Steps 4–8 use **"Time Delay"** — same meaning, just a naming inconsistency in the sheet. Don't be confused when you see both labels.

---

## 4. The 8 Payment Follow-Up Steps

### Step 1 — Is PDC Collected?
- **Who:** CRM
- **What:** There's a Google Form linked to this step. CRM fills the form to confirm whether the Post-Dated Cheque (PDC) has been collected from the customer.

### Step 2 — Is the Payment Received?
- **Who:** Accounts
- **What:** Accounts checks whether payment for the order has come in yet.

### Step 3 — Hard Stop on Sales & Change Credit Limit to 0
- **Who:** Accounts
- **What:** If the due date has passed and payment still hasn't been received, the same Accounts doer updates the customer's Credit Limit to **0** in Tally — this puts a hard stop on any further sales to that customer until resolved.

### Step 4 — Is the Payment Received? *(after credit hold)*
- **Who:** Accounts (with Sales/CRM continuing to call/remind the party)
- **What:** After the credit limit is set to 0, the company waits for payment while Sales/CRM keep following up with reminder calls. Once payment comes in, the Accounts doer checks and updates this step.

### Step 5 — Is the Buyer Credit Insured?
- **Who:** Accounts
- **What:** The same Accounts doer checks whether this customer's credit is insured, and marks the step done accordingly.

### Step 6 — Give Master Limit with Updated Limit to VJ
- **Who:** CRM
- **What:** CRM updates the master credit limit record and informs VJ Sir of the updated limit.

### Step 7 — Inform Credit Insured Broker
- **Who:** Accounts
- **What:** If the company/customer is credit-insured, the same Accounts doer informs the insurance broker/company about the situation.

### Step 8 — Re-Open Credit Limit
- **Who:** Accounts
- **What:** Once payment is confirmed received, the Accounts doer reviews the details and re-opens the customer's credit limit (reversing Step 3's hard stop).

---

## 5. Trailing Columns

| Column | Purpose |
|---|---|
| Doer_Email | Determines who is responsible for the task — used by AppSheet for task bifurcation/routing |
| How many days payment late received | Calculates actual delay vs. agreed payment terms (e.g. terms were 30 days, party paid on day 60 → this shows 30 days late) |
| Total Avg of Received Payment by party | Running average of how many days late this party typically pays |
| Total Order Value | Total value of the order — calculated as **Qty × Rate × 18%** (GST-inclusive value) |
| Total Pending Amount | Total amount still outstanding for that party across orders |
| Sales Executive Mail ID | Used for AppSheet task bifurcation to the correct SE |
| send_WA | Trigger/marker for sending a WhatsApp message |
| Mobile_No | Customer's contact number |
| Total Credit Limit | Party's total approved credit limit |
| Available Credit Limit | Remaining credit limit after current pending amount |
| Total No. of Order | Count of orders placed by this party |
| All Order | Reference/rollup of all orders for this party |
| Testing | Internal testing/staging column — not part of the live workflow |

---

## 6. Quick Reference — All 8 Steps at a Glance

| Step | Task | Owner | Trigger / Condition |
|---|---|---|---|
| 1 | Is PDC Collected? | CRM | Via linked Google Form |
| 2 | Is the Payment Received? | Accounts | Standard check after due date approaches |
| 3 | Hard Stop on Sales & Credit Limit → 0 | Accounts | Due date passed, payment not received |
| 4 | Is the Payment Received? (post credit-hold) | Accounts (+ Sales/CRM follow-up calls) | After Step 3, while awaiting payment |
| 5 | Is the Buyer Credit Insured? | Accounts | Checked once payment issue is confirmed |
| 6 | Give Master Limit update to VJ | CRM | After credit limit change |
| 7 | Inform Credit Insured Broker | Accounts | Only if buyer is credit-insured |
| 8 | Re-Open Credit Limit | Accounts | Once payment is confirmed received |

---

## 7. What a New Joinee Should Do

1. Open **D2C**, sort/filter by **Overdues Days** or **Pending Amount** to find parties needing urgent follow-up.
2. Check **Next Follow UP Date** — if it's due/overdue, that's an active call-back item.
3. If **Step 3 (Hard Stop)** shows Done but **Step 4 (Payment Received)** is still Not Done, that customer is currently on credit hold — don't process new sales for them without checking with Accounts.
4. Use **How many days payment late received** and **Total Avg of Received Payment by party** to flag chronically late-paying customers to management.

---

*End of SOP-007*
