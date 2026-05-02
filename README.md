# BurnPlan

**A free, private retirement planning calculator that runs entirely in your browser. Nothing is sent to any server. Your data never leaves your device.**

---

## Getting started

Open `index.html` in any modern browser. Fill in the **Setup** tab from top to bottom, then click **Run projections**. That's it — no account, no login, no install.

---

## Setup & assumptions

### Basic information
Enter your current age, retirement age, how long you want the plan to run (default 95), and your RMD start age (default 73). The app works whether you're pre-retired or already retired.

### Accounts
Add each account you hold — give it a name, current balance, and tax treatment:

| Tax treatment | Description |
|---|---|
| **Tax-deferred** | Traditional IRA, 401k — withdrawals taxed as ordinary income |
| **Tax-free (Roth)** | Withdrawals are tax-free |
| **Taxable LTCG** | Subject to capital gains tax on withdrawals |
| **Cash / Money market** | Grows at the inflation rate |

Optionally enter a **Return % override** for any account. Leave blank to use the global market assumption. Useful if one account is bonds-only, one is 100% stocks, or you hold a fixed-rate instrument.

### Pre-retirement contributions
Add annual contributions and employer match per account. Contributions stop automatically at your retirement age.

### Market assumptions
Set your expected inflation, stock return, and bond return. The app blends stock and bond returns based on your age, shifting toward bonds as you approach and enter retirement. You can also set how much to adjust returns for below-average and above-average market scenarios.

### Filing status timeline
Start with your initial filing status (single, married filing jointly, etc.). The standard deduction auto-fills. Add additional periods if your status changes at a later age — for example, after a spouse passes.

### Social Security
Enter your estimated annual benefit in **today's dollars** as shown on [ssa.gov](https://www.ssa.gov/myaccount/). Set your claim age and COLA rate. The app compounds COLA from your current age forward — so by the time you claim, the benefit already reflects years of cost-of-living increases.

### Other income streams
Add any income that will reduce your portfolio withdrawals — pension, rental income, part-time work, annuity, spousal SS, etc. Give each stream a name, start and end age, annual amount in today's dollars, COLA rate, and taxability. Each stream gets its own column in the projections table.

### Roth conversions
Model planned Roth conversions by specifying an age range, annual conversion amount, and your marginal tax bracket. The app estimates the annual tax cost.

### One-time events
Add irregular cash events that don't fit a regular schedule — an inheritance, a bonus, a home purchase, or a large gift. Specify the calendar year, a description, which account to affect, the amount, and whether it's a deposit or a withdrawal.

### Withdrawal schedule
Define the order in which accounts are drawn down during retirement. Each **period** specifies which accounts to use and what percentage of the net withdrawal need each covers. Periods run sequentially — not concurrently.

- **Fixed years** — this period runs for N years, then the next period begins
- **Until depleted** — this period runs until all its accounts are empty, then the next period begins

If an account within a period runs dry, the other accounts in that period absorb its share. When all scheduled accounts are exhausted, any remaining need is drawn from unscheduled accounts.

### Withdrawal scenarios
Define your annual spending target in today's dollars — the app inflates it automatically each year. Set multiple **spend steps** to model spending that changes over time:

> Example: $120,000 for the first 10 years → $100,000 for the next 10 → $85,000 for all remaining years

Add **comparison scenarios** to model different spending levels or step-down patterns side by side.

---

## Projections

After clicking **Run projections**, the Projections tab shows:

- **Summary metrics** — starting portfolio, ending value, portfolio peak, and ruin age (if applicable)
- **Market view** — switch between average, below average, above average, or all three overlaid on one chart
- **Plan selector** — switch between your base plan and any comparison scenarios
- **Chart** — portfolio balance by account over time
- **Account balances table** — year-by-year balance for every account plus total portfolio value. Accounts being actively drawn down are highlighted
- **Detail table** — full year-by-year breakdown including SS income, other income streams, one-time events, spend target, net portfolio withdrawal, RMDs, Roth conversions, and estimated federal taxes

### Estimated taxes include:
- Ordinary income tax on Traditional IRA / 401k withdrawals
- Taxable portion of Social Security (85% by default)
- Roth conversion tax at your specified marginal bracket
- Long-term capital gains tax on taxable account withdrawals

---

## Compare scenarios

The Compare tab overlays all your named spending scenarios on one chart. Switch between below average, average, and above average market views. Each scenario card shows its ending portfolio value, peak value, and ruin age.

---

## Stress tests

Define named crash events — specify the calendar year, drop percentage, and how many years the recovery takes. Run against any market scenario (below avg, average, above avg, or all three at once). The chart shows the stressed portfolio vs. the no-crash baseline side by side.

Recovery is modeled realistically: during recovery years, market returns are suppressed and ramp back up gradually. The lasting damage from a crash comes from being forced to sell assets at depressed prices to fund ongoing withdrawals.

Save any stress test result to the **Saved** tab for future reference.

---

## Import / Export

| Action | Description |
|---|---|
| **Export settings** | Downloads a JSON file with your complete plan configuration |
| **Import settings** | Loads a previously exported file and restores all inputs instantly |
| **Export CSV** | Downloads the full projection table as a spreadsheet |
| **Export PNG** | Saves any chart as an image file |

---

## Privacy

BurnPlan runs 100% in your browser. No accounts, no login, no servers. Your financial data never leaves your device.

The only external requests are loading [Chart.js](https://www.chartjs.org/) (charting library) and [Google Fonts](https://fonts.google.com/) from public CDNs. These load the interface — they receive no financial data.

---

## Disclaimer

BurnPlan is for **educational and planning purposes only**. It is not financial advice. Projections are estimates based on the assumptions you provide and do not guarantee future results. Consult a licensed financial advisor, CPA, or CFP before making retirement, investment, or tax decisions.

---

## Tech

- Single HTML file — HTML, CSS, and JavaScript with no build step, no framework, no dependencies to install
- [Chart.js](https://www.chartjs.org/) for visualizations (loaded from CDN)
- All data stored locally in your browser — nothing leaves your device
- Open source and auditable — right-click → View page source to see every formula