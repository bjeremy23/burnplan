# RetirePlan — Free Retirement Planning Calculator

A free, private, single-file retirement planning tool that runs entirely in your browser. No account required, no data sent to any server.

**[Run the calculator → bjeremy23.github.io/retireplan](https://bjeremy23.github.io/retireplan/)**

## Features

- Year-by-year portfolio simulation from current age to end of plan
- Supports pre-retirement (accumulation) and already-retired modes
- Multiple account types with tax treatment (Traditional IRA, Roth, Taxable, Cash/MM)
- Configurable withdrawal schedule — time-based periods with per-account percentage allocations
- Social Security income with COLA, applied from current age forward
- Other income streams — pension, annuity, rental, part-time, spousal SS
- Roth conversion modeling with marginal tax bracket estimation
- RMDs calculated using IRS Uniform Lifetime Table (SECURE 2.0, age 73)
- Below average / average / above average market scenario projections
- Stress testing — named crash events with drop % and recovery periods
- Withdrawal scenario comparison — overlay multiple spending plans on one chart
- Import / export settings as JSON — save and reload your plan
- Export projections as CSV, charts as PNG
- Filing status timeline with auto-filled standard deductions

## Running locally

No build step required — just open `index.html` in a browser.

```bash
open index.html
```
