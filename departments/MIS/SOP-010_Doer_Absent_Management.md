# SOP-010: Doer_Absent Management

**Document owner:** Prime MIS
**Applies to:** New MIS joinee
**File:** "Master_Sheet for all" → **Doer_Absent** tab

---

## 1. Purpose

This sheet tracks when a **doer (task owner) is on leave/absent**, and — most importantly — **who their tasks should be reassigned to** during that period. This is what allows AppSheet automation to reroute a task instead of it sitting unassigned/undone while the regular doer is away.

---

## 2. Column Reference

| Column | What it captures |
|---|---|
| Leave_ID | Auto-generated unique ID for this leave record (format: `{doer email}_{date}`) |
| Doer Mail | Email of the doer who is going on leave |
| Doer Name | Name of the doer |
| From Date | First day of absence |
| To Date | Last day of absence |
| Status | Current status of this leave record (e.g. "Absent") |
| Assigned To | Email of the person whose tasks will be temporarily reassigned/rerouted to during this leave period |

---

## 3. Example (from the sheet)

| Doer Name | From – To | Assigned To |
|---|---|---|
| PRIYA | 27-06-2026 (1 day) | admin2@primepoly.in |
| PRIYA | 07-07-2026 (1 day) | admin2@primepoly.in |
| ROBIN | 07-07-2026 (1 day) | accounts@primepoly.in |
| TANNU | 08-07-2026 to 15-07-2026 | crm2@primepoly.in |

This shows both **single-day absences** and **multi-day leave** (like TANNU's week-long leave) — the system covers both patterns the same way, just with a wider From/To Date range.

---

## 4. What a New Joinee Should Do

1. **Whenever a doer informs you they'll be absent**, add a new row here **before** their leave starts:
   - Fill in their **Doer Mail**, **Doer Name**, **From Date**, **To Date**
   - Set **Status** to "Absent"
   - Choose the correct **Assigned To** person — usually someone in the same department who can cover their tasks (see SOP-004/006/007 "Owner" columns to know who normally handles each step, and pick a suitable backup from that same role).
2. This directly affects the O2D, Purchase_FMS, and D2C step-tracking sheets (SOP-004, 006, 007) — while a doer is marked absent here, their pending tasks should be getting routed to the "Assigned To" person instead.
3. Double-check this list is up to date daily — an outdated or missing entry means a task could go unassigned and show as delayed/pending on the For PC or Master sheets.

---

*End of SOP-010*
