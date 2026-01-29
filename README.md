# Asset Management Lifecycle & Cash Flow Controls (Excel)

## Overview
This project simulates a front-to-back asset management operations control framework focused on trade settlement, cash movement, and reconciliation.

The objective is to demonstrate operational risk awareness, control design, and reconciliation logic — not performance analytics.

## Key Components
- Trade capture and settlement tracking
- Expected vs actual cash reconciliation
- Timing vs true break classification
- Exception taxonomy (Missing Cash, Amount Difference, Timing Difference)
- Daily control summary with traffic-light status

## Sheets Breakdown
- Lifecycle_Overview: End-to-end asset lifecycle and control ownership
- Trade_Log: Executed trades and expected cash logic
- Cash_Movements: Custodian-reported cash activity
- Cash_Reconciliation: Expected vs actual cash control checks
- Control_Summary: Daily operational control status

## Controls Implemented
- Buy/Sell directional cash logic
- Settlement date-based timing controls
- Aggregated cash movement reconciliation
- Exception classification and escalation logic
- Management-level control reporting

## Tools Used
- Microsoft Excel
- XLOOKUP, SUMIF, FILTER, MAXIFS
- Conditional formatting for control visibility

## Use Case
This project mirrors real-world asset management operations workflows commonly found in investment banks and asset managers.
