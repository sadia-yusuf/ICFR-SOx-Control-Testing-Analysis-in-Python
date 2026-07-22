# ICFR / SOx Control Testing — Analysis in Python

An internal-controls-over-financial-reporting (ICFR) testing programme analysed
**end to end in Python**. From a Risk Control Matrix of 35 controls with test
results, the notebook measures control health and produces a management view:
pass rates, deficiency severity, design-vs-operating split, manual-vs-automated
performance, and remediation aging.

Built by a Chartered Accountant to show controls-assurance analytics done directly in code.

## Files

| File | Description |
|------|-------------|
| `icfr_control_testing_data.csv` | **The dataset** — a fixed Risk Control Matrix of 35 controls across 6 processes, with test results (ready to use, no generation needed) |
| `icfr_control_testing_analysis.ipynb` | The analysis notebook — all calculations and charts in Python, outputs pre-executed |
| `ICFR_Control_Testing_Tracker.xlsx` | *(optional)* the same dataset as an Excel tracker + summary, if you want to attach it too |

> The Excel file is built from the same CSV, so every number reconciles between
> the notebook and the workbook.

## The dataset (`icfr_control_testing_data.csv`)

One row per control, documented as an assurance team documents it:

`Control_ID · Process · Risk_ID · Risk_Description · Control_Description · Control_Owner ·
Control_Type (Preventive/Detective) · Control_Nature (Manual/Automated) · Frequency ·
Assertion · Test_Procedure · Population_Size · Sample_Size · Exceptions_Noted ·
Test_Date · Tester · Test_Result (Pass/Exception/Fail) · Deficiency_Type (Design/Operating) ·
Deficiency_Severity · Remediation_Owner · Remediation_Due_Date · Remediation_Status`

Processes: Procure-to-Pay, Order-to-Cash, Payroll, Financial Close, ITGC, Treasury.
Analysis "as of" date: **30 Sep 2025** (used for overdue calculations).

## Run it

```bash
pip install pandas numpy matplotlib
jupyter notebook icfr_control_testing_analysis.ipynb   # or open in VS Code
```

The notebook already has outputs embedded, so it renders fully on GitHub without re-running.

## What the analysis produces

1. **Headline KPIs** — pass rate, deficiency count, high-severity count, overdue remediations.
2. **Test-result distribution** — Pass / Exception / Fail donut.
3. **Pass rate by process** — where the control environment is weakest (the key risk view).
4. **Deficiency severity + design-vs-operating** — design deficiencies flagged as more serious.
5. **Manual vs automated performance** — quantifies where automation reduces risk.
6. **Remediation aging** — open items past due date, ranked.
7. **Prioritised remediation worklist** — severity- and overdue-sorted, ready for management.

## How this maps to a controls-assurance role
- **Design & operating-effectiveness testing** — captured per control, split by deficiency type.
- **Risk-based prioritisation** — severity and overdue days drive the worklist.
- **Coverage & consistency** — one test logic across every control and process.
- **Stakeholder reporting** — KPIs, charts and a worklist a senior manager can read at a glance.
