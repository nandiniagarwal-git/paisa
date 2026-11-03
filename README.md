# Paisa

A budgeting app for college students. Track your allowance and side income, bills, debts, savings goals and everyday spending, then see what's safe to spend each day. It also uses basic economics to show how well your spending matches what you value.

**Live app:** https://paisaaapp.netlify.app
**Built by:** NANDINI AGARWAL

---

## What it does

| Section | What you can do |
|---|---|
| Income | Add any number of sources, such as allowance, brand sales or a stipend |
| Everyday expenses | Log spending as Needs or Wants, edit or delete any entry |
| Bills | Add daily, monthly or yearly bills. The app converts each one to a monthly cost |
| Unavoidable costs | Track fixed costs like rent, commute and phone recharge |
| Debts and loans | Set total, amount paid and monthly EMI. See progress and payments left, and tap "Pay EMI" to log a payment |
| Savings target | Set a goal, a target and a monthly amount. See how many months remain |
| Budget | Split income into Needs, Wants, Debt and Savings by percentage. Bars show how much of each you've used, and turn red when you go over |
| Monthly tracking | Switch between months and compare income against spending for the last six |
| Safe to spend per day | Shows what you can spend each day for the rest of the month |
| Calculator | A built-in calculator that can send its result to the expense form |
| Can I afford it? | Enter a price and see how many days of budget it costs and how much it delays your savings goal |
| Backup | Export and import your data as a JSON file |

The app starts empty. Everything you see is something you added.

## The economics behind it

The app turns a few ideas from introductory microeconomics into live charts.

**Budget line.** Your flexible money is what's left after fixed costs, bills, EMIs and your savings contribution:

```
M = income - bills - fixed costs - EMIs - monthly savings
```

All of it can go to flexible Needs (N) or Wants (W), so the budget line is `N + W = M`.

**Indifference curves.** Your taste for Wants is modelled with a Cobb-Douglas utility function:

```
U = N^(1 - a) * W^a
```

You set `a` with the "How much do you value wants?" slider. The utility-maximizing split is `W = a * M` and `N = (1 - a) * M`. The chart draws the budget line, three indifference curves (one below, one at the optimum, and one out of reach) and your actual spending as a dot, so you can see how far you are from the best mix.

**Opportunity cost.** The "Can I afford it?" tool translates a price into days of daily budget and days of delay on your savings goal.

**Other formulas.** Daily bills are multiplied by 30 and yearly bills divided by 12 to get a monthly cost. Safe to spend per day is flexible money left divided by days left in the month.

## Tech stack

Plain HTML, CSS and JavaScript. No frameworks, no build step, no dependencies.

| Piece | How it's used |
|---|---|
| Vanilla JavaScript | All app logic, DOM rendering and the calculator |
| Inline SVG | The budget line and indifference curve chart |
| CSS grid and flexbox | A responsive layout from phone to desktop |
| localStorage | Saves your data on your device |
| Web App Manifest | Makes the app installable |
| Service worker | Caches the app so it works offline |

## Skills this project shows

Vibe and AI coding to build - UI and data visualization; applying economic theory in code; building a Progressive Web App (PWA); and personal finance modelling.

## Project structure

```
paisa/
  index.html                  The whole app: markup, styles and logic
  manifest.webmanifest        Install settings, name and icons
  sw.js                       Service worker for offline use
  icon-192.png                App icon
  icon-512.png                App icon
  icon-maskable-512.png       Icon for Android adaptive shapes
  README.md
```

## Run it locally

```
cd paisa
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Deploy on GitHub Pages

1. Push these files to a repository.
2. Go to Settings, then Pages.
3. Under Source, choose the main branch and the root folder, and save.
4. After a minute, your app is live at `https://YOUR-USERNAME.github.io/REPO-NAME/`.

Installing the app needs HTTPS, which GitHub Pages provides.

## Install on your phone

**Android (Chrome):** open the link, then tap "Install app" at the bottom of the page or use the browser menu.
**iPhone (Safari):** tap Share, then Add to Home Screen.

After the first load it works offline.

## Data and privacy

Everything is stored in your browser's localStorage on your own device. Nothing is sent to a server, and there are no accounts. This also means data does not sync between devices. Use Export backup to save a copy or move to a new phone, and Import backup to restore it. Clearing your browser data erases your entries.

## Known limitations

No multi-user or cloud sync, and no bank or SMS import. The monthly view assumes your income, bills and fixed costs repeat every month. Currency is Indian rupees.

## Ideas for later

Recurring expenses that add themselves, spending categories beyond Needs and Wants, CSV export for analysis in Python or R, charts by category, and optional cloud sync.

## How it was built

The design was prototyped on a canvas and the code was written with the help of Claude (an AI assistant) from my feature list and requirements. I specified the features, the economics concepts and the structure, and reviewed and adjusted the result.
