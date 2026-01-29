# Asset Management Lifecycle & Cash Flow Controls (Excel + Power BI)

## Overview
This project implements a **front-to-back asset management operations control framework** covering trade execution, settlement, cash movement, and reconciliation.

The objective is to demonstrate **operational lifecycle understanding, control design, exception handling, and management reporting** — not performance analytics or portfolio optimization.

The solution is intentionally split into two layers:
- **Excel** as the system of record and control engine
- **Power BI** as the management monitoring and exception triage layer

The framework is **prebuilt to support up to 20 trades per daily processing cycle**.  
The included sample run uses **6 representative trades** to clearly demonstrate all key control outcomes (PASS, TIMING differences, and true settlement BREAKs) without unnecessary duplication.

---

## Business Context
In asset management and investment banking operations, daily cash reconciliation controls are critical to:
- Ensure trades settle correctly
- Confirm cash moves in the correct amount and currency
- Distinguish timing differences from true settlement breaks
- Quantify operational risk exposure
- Escalate issues through clear control reporting

This project mirrors workflows commonly used by **Operations, Middle Office, and Asset Servicing teams** to monitor settlement risk and report control status to management.

---

## Solution Architecture

### Excel — Control Engine
Excel serves as the **system of record**, where all reconciliation logic and controls are calculated for auditability and transparency.

### Power BI — Monitoring & Reporting
Power BI sits on top of the Excel outputs to provide **management visibility**, **exception monitoring**, and **risk-focused dashboards** without recreating reconciliation logic.

This separation reflects real-world operational design principles.

---

## Excel Workbook Structure

### Lifecycle_Overview
Defines the end-to-end asset lifecycle:
- Trade execution
- Trade validation
- Settlement instruction
- Cash movement
- Reconciliation and controls  

Includes ownership and control objectives at each stage.

---

### Trade_Log
Represents executed trades and expected settlement cash:
- Buy/Sell directional cash logic
- Settlement date–based expected cash calculations
- Currency-level controls

---

### Cash_Movements
Represents custodian-reported cash activity:
- Actual cash movements
- Value-date recognition
- Support for delayed or partial settlements

---

### Cash_Reconciliation
Core control layer:
- Expected vs actual cash reconciliation
- Timing difference vs true break classification
- Exception taxonomy:
  - Missing Cash
  - Amount Difference
  - Timing Difference

---

### Control_Summary
Management-level control snapshot:
- Daily trade volume
- Unreconciled trade count
- Total cash exposure
- Overall control status (Green / Amber / Red)

---

## Power BI Dashboard

### Dashboard File
- `Cash_Reconciliation_Control_Dashboard.pbix`

### Page 1 — Cash_Reconciliation_Dashboard
Executive-level control view providing a daily snapshot of reconciliation health:
- Total trades processed
- Unreconciled trades
- Total cash difference (exposure)
- Overall control status (traffic-light logic)

This page answers:
> “Are we under control today?”

---

### Page 2 — Exception Monitoring
Operational triage view used by Ops teams to investigate issues:
- Trade-level exception table
- PASS / TIMING / BREAK classification
- Break Type categorization
- Interactive slicers for Status and Break Type
- Conditional formatting to highlight financial exposure

This page answers:
> “What is broken, why, and where should attention be focused?”

---

## Controls Implemented
- Buy/Sell directional cash treatment
- Settlement date–based timing controls
- Aggregated cash movement reconciliation
- Clear separation of timing differences vs true breaks
- Exception classification aligned to operational risk
- Daily control escalation via traffic-light reporting

---

## Sample Outcomes Demonstrated
The sample data intentionally includes:
- Fully reconciled trades (PASS)
- Late-settling trades (TIMING differences)
- Missing cash scenarios
- Amount mismatches requiring investigation

This allows the control framework to be evaluated across all common operational scenarios.

---

## Tools & Technologies
- Microsoft Excel (control logic and reconciliation)
- Microsoft Power BI (monitoring and reporting)
- Power Query (data hygiene only)
- XLOOKUP, SUMIF, MAXIFS
- Conditional formatting and slicers for exception visibility

---

## Intended Audience
This project reflects real-world workflows used by:
- Asset Management Operations
- Middle Office / Trade Support
- Fund Accounting
- Settlement & Reconciliation teams

---

## Notes on Design
The framework is intentionally structured with **prebuilt processing capacity** beyond the sample data.  
Unused rows represent **daily batch headroom**, consistent with how operational control files are maintained in practice.

Excel remains the **audit-friendly control layer**, while Power BI provides **management insight without altering core logic**.
