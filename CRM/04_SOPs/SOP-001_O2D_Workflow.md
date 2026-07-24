# SOP-001 – Order to Dispatch (O2D) Workflow

**Document Version:** 1.0
**Project:** Prime Polymart CRM AI Assistant
**Department:** Customer Relationship Management (CRM)
**Process Name:** Order to Dispatch (O2D) Workflow
**Status:** Active

---

# Purpose

The Order to Dispatch (O2D) Workflow is the company's workflow management process used to monitor, assign, and complete customer orders from order receipt until successful delivery confirmation.

This SOP defines the responsibilities of CRM and other departments, business rules, workflow logic, and system behaviour followed at Prime Polymart.

---

# Scope

This SOP applies to all customer sales orders processed through the O2D workflow.

The workflow involves coordination between:

* CRM
* Accounts
* Logistics

---

# Trigger

The O2D workflow starts after:

1. Sales Executive shares the confirmed customer order in the official WhatsApp Order Group.
2. Assigned CRM Executive receives the order.
3. CRM creates the Sales Order in Tally.
4. CRM fills the AppSheet Sales Order Form.
5. Data is automatically transferred to the Master Sheet.
6. Order is automatically reflected in the O2D Sheet.

Only after these activities does the O2D workflow begin.

---

# O2D Sheet Structure

Each workflow step contains the following five system columns.

## 1. Planned

The target completion time assigned by the company for a particular task.

* It represents the deadline within which the assigned person (Doer) should complete the task.
* The planned time is generated automatically.
* Every step may have a different target time.
* It can range from one hour to multiple days depending on the process.

---

## 2. Actual

The actual date and time when the assigned person completed the task.

---

## 3. Status

The assigned person updates this column after completing the task.

Examples:

* Done
* Yes
* Completed

Status values may vary according to the workflow requirement.

---

## 4. Time Delay

Automatically calculates the difference between Planned and Actual completion time.

This helps measure task performance and SLA compliance.

---

## 5. Done By

Automatically captures the email ID of the user who updates the Status column.

This provides complete accountability and activity tracking.

---

# Business Rules

The following rules are mandatory.

* Never update **Status** if the **Planned** column is blank.
* Perform only those steps where **Planned** is generated.
* Never skip mandatory workflow steps.
* Do not manually update **Done By**.
* Do not manually calculate **Time Delay**.
* Follow the sequence of workflow steps.
* Use only company-approved communication templates.
* Do not proceed with unauthorized approvals.

---

# Workflow Steps

## Step 1 – Increase Credit Limit / Receive Advance Payment

**Department:** CRM

### Condition

This step appears only when the customer's credit limit is exceeded.

### Process

1. Verify that the Planned column is generated.
2. Check the customer's credit limit.
3. Contact the authorized Director for approval.
4. Wait for approval or advance payment.
5. After approval or payment, update the Status column.
6. Workflow proceeds to the next step.

### Important Rule

CRM does not approve the credit limit.

Only the authorized management can approve credit enhancement.

---

## Step 2 – Send Sales Order to Customer & Update SO in Tally

**Department:** CRM

### Process

1. Receive the order from the official WhatsApp Order Group.
2. Create the Sales Order in Tally.
3. Open the approved Sales Order WhatsApp template.
4. Send the Sales Order confirmation to the customer.
5. The message is sent for verification of:

   * Product
   * Quantity
   * Rate
   * Delivery details
   * Other order information
6. Update the Status after completing the activity.

### Note

Customer reply is optional.

The purpose is to provide confirmation before invoice generation and maintain communication records.

---

## Step 3 – Material Load and Send for Invoice

**Department:** Logistics

### CRM Responsibility

No action required.

---

## Step 4 – Make Invoice & Mail

**Department:** Accounts

### CRM Responsibility

No action required.

---

## Step 5 – Send Invoice on WhatsApp

**Department:** CRM

### Condition

This step appears only when Planned is generated.

### Process

1. Verify invoice has been generated.
2. Check whether the customer requires WhatsApp invoice sharing.
3. Open the approved WhatsApp Invoice template.
4. Send the invoice.
5. Update the Status column.

### Business Rule

* Customer → Invoice may be shared on WhatsApp.
* Trader → Invoice is generally shared through email only.

Follow the company workflow applicable to the customer category.

---

## Step 6 – Buy Insurance

**Department:** Accounts

### CRM Responsibility

No action required.

---

## Step 7 – MTC Status

**Department:** Accounts

### CRM Responsibility

No action required.

---

## Step 8 – Confirm Delivery from Transporter

**Department:** Logistics

### CRM Responsibility

No action required.

---

## Step 9 – Confirm Delivery to Customer

**Department:** CRM

### Condition

This step appears only when Planned is generated.

### Process

1. Open the approved Delivery Confirmation WhatsApp template.
2. Send the confirmation message to the customer.
3. Request delivery confirmation and customer feedback.
4. Update the Status after sending the message.

### Business Rule

Customer reply is **not mandatory**.

Status should be updated after the confirmation message has been successfully sent.

---

# Department Responsibility Matrix

| Step | Activity                               | Department |
| ---- | -------------------------------------- | ---------- |
| 1    | Credit Limit / Advance Payment         | CRM        |
| 2    | Sales Order Confirmation               | CRM        |
| 3    | Material Loading                       | Logistics  |
| 4    | Invoice Generation                     | Accounts   |
| 5    | Invoice Sharing                        | CRM        |
| 6    | Insurance                              | Accounts   |
| 7    | MTC Status                             | Accounts   |
| 8    | Delivery Confirmation from Transporter | Logistics  |
| 9    | Delivery Confirmation to Customer      | CRM        |

---

# AI Guidance Rules

When answering O2D-related questions, the AI must:

1. Identify the current workflow step.
2. Check whether the Planned column is generated.
3. Explain the responsibility of the current department.
4. Provide only the actions required for that step.
5. Never suggest skipping workflow steps.
6. Never recommend unauthorized approvals.
7. Follow Prime Polymart's approved workflow.

---

# Common Mistakes

* Updating Status when Planned is blank.
* Skipping workflow steps.
* Using unofficial WhatsApp messages.
* Updating Status before completing the task.
* Attempting to approve credit without authorization.

---

# Escalation

Escalate to the authorized person when:

* Credit approval is required.
* Workflow is blocked.
* Planned is generated but the task cannot be completed.
* System issues prevent workflow completion.

---

# Revision History

| Version | Description              |
| ------- | ------------------------ |
| 1.0     | Initial O2D Workflow SOP |
