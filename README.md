# Asset Management Lifecycle & Cash Flow Controls (Excel)

## Overview
This project simulates a **front-to-back asset management operations control framework** focused on trade settlement, cash movement, and reconciliation.

The objective is to demonstrate **operational lifecycle understanding, control design, and exception handling** — not performance analytics or portfolio optimization.

The workbook is **prebuilt to support up to 20 trades per daily processing cycle**.  
The included sample run uses **6 representative trades** to intentionally demonstrate all key control outcomes (PASS, TIMING difference, and true settlement BREAKs) without unnecessary duplication.

---

## Business Context
In asset management and investment banking operations, daily controls are used to ensure:
- Trades settle correctly
- Cash moves in the correct amount and currency
- Timing differences are distinguished from true breaks
- Exceptions are identified, classified, and escalated appropriately

This project mirrors how **Operations / Middle Office / Asset Servicing teams** monitor settlement risk and report control status to management.

---

## Workbook Structure

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
- Settlement date–based expected cash
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
- Expected vs actual cash comparison
- Timing difference vs true break classification
- Exception taxonomy:
  - Missing Cash
  - Amount Difference
  - Timing Difference

---

### Control_Summary
Management-level control view:
- Daily trade and cash volume
- Count of unreconciled trades
- Total cash exposure
- Traffic-light control status (Green / Amber / Red)

---

## Controls Implemented
- Buy/Sell directional cash treatment
- Settlement date–based timing controls
- Aggregated cash movement reconciliation
- Clear separation of timing differences vs true breaks
- Exception classification aligned to operational risk
- Daily control reporting suitable for management review

---

## Sample Outcomes Demonstrated
The sample data intentionally includes:
- Fully reconciled trades (PASS)
- Late-settling trades (TIMING differences)
- Missing cash scenarios
- Amount mismatches requiring investigation

This allows the control logic to be evaluated across all common operational scenarios.

---

## Tools & Techniques
- Microsoft Excel
- XLOOKUP, SUMIF, FILTER, MAXIFS
- Conditional formatting for control visibility
- Scalable control logic designed for daily batch processing

---

## Intended Use
This project reflects **real-world asset management and investment banking operations workflows**, similar to those used in:
- Middle Office
- Asset Servicing
- Fund Accounting
- Settlement & Reconciliation teams

---

## Notes on Design
The workbook is intentionally structured with **prebuilt capacity** beyond the sample data.  
Unused rows represent **daily processing headroom**, consistent with how operational control files are maintained in practice.

