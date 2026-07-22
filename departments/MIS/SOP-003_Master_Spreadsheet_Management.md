# SOP-003: Master Spreadsheet Management

**Document owner:** Prime MIS
**Applies to:** New MIS joinee
**File name:** **"Master_Sheet for all"** (Google Sheet, also connected to AppSheet)

---

## 1. Purpose

This is the **central operations file** for Prime Polymart's sales-to-delivery process. It holds every sheet related to the order lifecycle — from the moment a sale order is placed, through dispatch, invoicing, and delivery confirmation.

This SOP gives a **basic orientation** to all the tabs in this file so a new joinee knows what each one is for. Detailed step-by-step SOPs for the more complex sheets (O2D, D2C, etc.) will follow separately.

---

## 2. How Orders Enter the System

Sale orders are **not typed directly into this spreadsheet**. They come in through a **form** — originally an HTML/Google Form, now via **AppSheet** — and the submission automatically creates a new row on the **Sale_Form** tab. This is the starting point of every order's journey through the system.

---

## 3. Tabs in This File — Quick Overview

| Tab Name | Purpose (basic) |
|---|---|
| **Sale_Form** 🔒 | Raw sale order data as submitted via AppSheet/Form. Entry point for every order. |
| **O2D** 🔒 | "Order to Delivery" — tracks each order through 9 fulfillment steps (credit limit → delivery confirmation). Covered in detail in **SOP-004**. |
| **Purhase_Form** 🔒 | Purchase order entries (raw material buying side). |
| **Purchase_FMS** | Purchase order tracking/follow-up management. |
| **D2C** 🔒 | Direct-to-customer order tracking (separate workflow from O2D — covered in a future SOP). |
| **Current Credit Limit** | Reference sheet showing each customer's approved credit limit — used by the O2D "Increase Credit Limit" step. |
| **Company_Name** | Master list of company/customer names used for dropdowns across the file. |
| **Doer_Absent** | Marks which doer is on leave — used so tasks aren't assigned to an absent person. |
| **Product_Name** | Master list of product names used for dropdowns. |
| **Form_Menu** | Backend settings/menu configuration for the AppSheet form. |
| **SE_Doer_Map** | Maps each Sales Executive (SE) to the correct Doer/department — used for auto-routing tasks. |

> 🔒 = restricted/protected tab (edit access limited to specific roles — check with admin before editing directly).

---

## 4. Sale_Form Tab — Column Reference

This is the raw order data captured at the point of sale. Columns (left to right):

| # | Column | What it captures |
|---|---|---|
| 1 | Time Stamp | Date/time the order was submitted |
| 2 | Unique Key | Auto-generated ID for the order row (e.g. PPPL1) |
| 3 | Order No | Internal order number |
| 4 | Company Name | Customer/buyer company |
| 5 | Sales Executive | Which SE booked the order |
| 6 | Product | Product name/grade ordered |
| 7 | Qty (In Kg) | Order quantity |
| 8 | Rate | Price per kg |
| 9 | Credit Note (Amount) | Any credit note tied to the order |
| 10 | Delivery Type (Self/By Us) | Whether customer picks up (SELF) or we deliver (BY US) |
| 11 | Delivery Charges | Freight/delivery cost, if applicable |
| 12 | Unloading Labour | Unloading charge details |
| 13 | Mtc | Whether Material Test Certificate is required |
| 14 | P T (Payment Terms) | Days of credit/payment terms |
| 15 | Delivery On Date? | Expected delivery date |
| 16 | Customers/Trader | Whether the buyer is a direct customer or a trader |
| 17 | Pdc | Post-dated cheque status |
| 18 | Remarks | Free-text notes on the order |
| 19 | Ship To Address:- | Delivery address |

This same order data then flows into the **O2D** tab, where it's tracked through fulfillment (see SOP-004).

---

## 5. What a New Joinee Should Do First

1. Get view/edit access confirmed for each tab you'll actually work on (some are 🔒 restricted).
2. Familiarize yourself with **Sale_Form** column names above — you'll see the same fields repeated across O2D and D2C.
3. Move to **SOP-004 (O2D Management)** to understand how an order is tracked after it's placed.

---

*End of SOP-003*
