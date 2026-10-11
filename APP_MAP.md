# App map

Every screen of the app, in order, with the exact Hebrew labels (English in brackets), what each element does and the path to it. Stable ids (`page` / `page.section`) let a chat say navigate("portfolio", "import").

## Bottom tabs
- `today` **🏠 היום** (Today): one screen: status light + TQQQ/$570 sentence, my money, what changed, Claude says, today's top 5
- `top5` **🔥 Top 5** (Top 5): the virtual $10,000 test of the daily top 5 (App / Claude), open and closed positions, my watchlist
- `portfolio` **💼 התיק שלי** (My money): net worth, a card per holding, allocation, broker import, editing (trade, deposits, holdings, accounts, undo), TQQQ rules
- `tune` **🎯 כוונון** (Tune): benchmark, screener preferences + preview, my own alerts, instructions to Claude, live chat (coming soon)
- `more` **⋯ עוד** (More): the list of every other screen + language + reload + download my data

## Under ⋯ עוד (More), in order
- `overview` **📋 סקירה מלאה** (Full overview): the previous home page: summary, mood, hot 5 cards, stay-away 5
- `stock` **📊 מניה** (Stock details): any stock: score + plain sentence, fundamentals, chart, factor bars, news vs Claude, insiders, headlines
- `report` **📰 דוח הבוקר** (Morning report): morning Claude's full report, archive by date, that day's picks, Open in Google Drive
- `weekly` **📅 סיכום שבועי** (Weekly summary): every Friday's weekly summary
- `activity` **📜 הפעילות שלי** (My activity): my full activity timeline: filters, search, monthly summary, CSV/Excel
- `track` **🏆 הצלחה** (Track record): hit rate over time, what the app learned, paper portfolio, App vs Claude vs benchmark, Claude's journal
- `smart` **💰 כסף חכם** (Smart money): insider buys, buybacks, big funds (13F)
- `sectors` **🌍 סקטורים** (Sectors): which sectors are hot or cold
- `history` **📜 היסטוריה** (History): similar market periods since 1990 and event base rates
- `advanced` **⚙️ מתקדם** (Advanced): the original English tables: overview, research, track record, charts, backtest, log, connections
- `connections` **🔌 חיבורים** (Connections): is everything connected: data, GitHub run, public feed, data check, Claude picks/report today

## Screens in detail
### `today` — 🏠 היום (Today)
one screen: status light + TQQQ/$570 sentence, my money, what changed, Claude says, today's top 5
- `today.status` **הכול בסדר** (All good, card): traffic light: green ok / yellow close to a rule / red rule broken or signal changed  
  path: 🏠 היום → הכול בסדר
- `today.money` **שווי החשבון** (Account value, card): account value, today's change, profit vs deposits  
  path: 🏠 היום → שווי החשבון
- `today.changed` **🔄 מה השתנה מאתמול** (🔄 What changed since yesterday, card): up to 5 bullets of what changed since yesterday  
  path: 🏠 היום → 🔄 מה השתנה מאתמול
- `today.claude` **🧠 Claude אומר** (🧠 Claude says, card): 3 lines from the morning report; 'Full report' opens 📰  
  path: 🏠 היום → 🧠 Claude אומר
- `today.top5` **ה-Top 5 של היום** (Today's top 5, chips): today's top 5 tickers; tap -> 🔥 Top 5  
  path: 🏠 היום → ה-Top 5 של היום

### `top5` — 🔥 Top 5 (Top 5)
the virtual $10,000 test of the daily top 5 (App / Claude), open and closed positions, my watchlist
- `top5.who` **האפליקציה** (App, toggle): App / Claude: whose picks the test shows  
  path: 🔥 Top 5 → האפליקציה
- `top5.value` **שווי התיק הווירטואלי** (Virtual portfolio value, card): virtual value, return, vs the benchmark  
  path: 🔥 Top 5 → שווי התיק הווירטואלי
- `top5.open` **פוזיציות פתוחות** (Open positions, list): open positions by buy day (day x/5); tap a ticker -> stock details  
  path: 🔥 Top 5 → פוזיציות פתוחות
- `top5.closed` **עסקאות שנסגרו** (Closed trades, list): closed trades with ✓/✗ vs the benchmark  
  path: 🔥 Top 5 → עסקאות שנסגרו
- `top5.watchlist` **👀 רשימת המעקב שלי** (👀 My watchlist, list): my watchlist with today's alerts  
  path: 🔥 Top 5 → 👀 רשימת המעקב שלי

### `portfolio` — 💼 התיק שלי (My money)
net worth, a card per holding, allocation, broker import, editing (trade, deposits, holdings, accounts, undo), TQQQ rules
- `portfolio.totals` **שווי כולל** (Net worth, card): net worth, money in, profit, time-weighted return  
  path: 💼 התיק שלי → שווי כולל
- `portfolio.holdings` **החזקות** (Holdings, cards): a card per holding with value and P&L  
  path: 💼 התיק שלי → החזקות
- `portfolio.allocation` **חלוקה וחשיפה** (Allocation & exposure, expander): shares by ticker/type/sector/account, exposure, concentration limit slider  
  path: 💼 התיק שלי → חלוקה וחשיפה
- `portfolio.import` **ייבוא קובץ מהברוקר** (Import from your broker, expander): upload CSV/XLSX/XLS -> column matching -> label unknown codes -> preview -> choose merge / use file / keep -> אשר ושמור  
  path: 💼 התיק שלי → ייבוא קובץ מהברוקר
- `portfolio.trade` **עסקה חדשה** (New trade, tab): form: buy/sell, account, ticker, shares, price, date, type -> save trade  
  path: 💼 התיק שלי → עסקה חדשה
- `portfolio.deposits` **הפקדות** (Deposits, tab): table of deposits/withdrawals (amount < 0 = withdrawal) -> save changes  
  path: 💼 התיק שלי → הפקדות
- `portfolio.holdings_edit` **החזקות** (Holdings, tab): table of holdings (edits are marked manual) -> save changes  
  path: 💼 התיק שלי → החזקות
- `portfolio.accounts` **חשבונות** (Accounts, tab): table of accounts -> save changes  
  path: 💼 התיק שלי → חשבונות
- `portfolio.history` **היסטוריה** (History, tab): undo the last change + the change history  
  path: 💼 התיק שלי → היסטוריה
- `portfolio.charts` **חלוקה ושווי לאורך זמן** (Allocation and value over time, expander): pies and value over time  
  path: 💼 התיק שלי → חלוקה ושווי לאורך זמן
- `portfolio.rules` **TQQQ והכללים** (TQQQ and the rules, expander): TQQQ positions, exposure gauge, $570 floor and rules A-E  
  path: 💼 התיק שלי → TQQQ והכללים
- `portfolio.download` **הורד את הנתונים שלי (zip)** (Download my data (zip), button): download every data file as a zip  
  path: 💼 התיק שלי → הורד את הנתונים שלי (zip)

### `tune` — 🎯 כוונון (Tune)
benchmark, screener preferences + preview, my own alerts, instructions to Claude, live chat (coming soon)
- `tune.benchmark` **מול מה משווים** (What we compare with, select): QQQ / SPY / cash / sector ETF: every 'vs' number uses it (saved at once)  
  path: 🎯 כוונון → מול מה משווים
- `tune.preferences` **ההעדפות שלך** (Your preferences, form): focus/avoid sectors, risk, horizon, picks per day, watchlist, exclude -> save; preview of today's top  
  path: 🎯 כוונון → ההעדפות שלך
- `tune.alerts` **🔔 התראות משלך** (🔔 Your own alerts, form): ticker + rule (above/below/move/50-200 cross/insider) + urgent -> add; ✕ deletes  
  path: 🎯 כוונון → 🔔 התראות משלך
- `tune.instructions` **🧠 הנחיה ל-Claude** (🧠 Instructions for Claude, form): text -> send to Claude (public file); answers appear under each item  
  path: 🎯 כוונון → 🧠 הנחיה ל-Claude
- `tune.chat` **צ'אט חי (בקרוב)** (Live chat (coming soon), card): live chat: coming soon  
  path: 🎯 כוונון → צ'אט חי (בקרוב)

### `more` — ⋯ עוד (More)
the list of every other screen + language + reload + download my data
- `more.list` **עוד** (More, list): every other screen  
  path: ⋯ עוד → עוד
- `more.language` **שפה** (Language, radio): עברית / English  
  path: ⋯ עוד → שפה
- `more.reload` **רענון נתונים** (Reload data, button): reload the data  
  path: ⋯ עוד → רענון נתונים
- `more.download` **הורד את הנתונים שלי (zip)** (Download my data (zip), button): download my data (zip)  
  path: ⋯ עוד → הורד את הנתונים שלי (zip)

### `overview` — ⋯ עוד → 📋 סקירה מלאה (Full overview)
the previous home page: summary, mood, hot 5 cards, stay-away 5

### `stock` — ⋯ עוד → 📊 מניה (Stock details)
any stock: score + plain sentence, fundamentals, chart, factor bars, news vs Claude, insiders, headlines
- `stock.pick` **בחר מניה** (Pick a stock, select): choose any stock (🔥 hot, 🧊 cold)  
  path: ⋯ עוד → 📊 מניה → בחר מניה
- `stock.fundamentals` **📑 דוחות כספיים** (📑 Fundamentals, card): revenue, margins, debt, P/E (n/a = missing)  
  path: ⋯ עוד → 📊 מניה → 📑 דוחות כספיים
- `stock.breakdown` **ממה מורכב הציון** (What the score is made of, card): each factor bar with a one-line meaning; app news vs Claude rating  
  path: ⋯ עוד → 📊 מניה → ממה מורכב הציון

### `report` — ⋯ עוד → 📰 דוח הבוקר (Morning report)
morning Claude's full report, archive by date, that day's picks, Open in Google Drive
- `report.date` **איזה דוח להציג** (Which report, select): which day's report  
  path: ⋯ עוד → 📰 דוח הבוקר → איזה דוח להציג
- `report.drive` **פתח ב-Google Drive** (Open in Google Drive, link): Google Drive search  
  path: ⋯ עוד → 📰 דוח הבוקר → פתח ב-Google Drive
- `report.picks` **הבחירות של Claude ליום הזה** (Claude's picks for this day, table): that day's structured picks  
  path: ⋯ עוד → 📰 דוח הבוקר → הבחירות של Claude ליום הזה

### `weekly` — ⋯ עוד → 📅 סיכום שבועי (Weekly summary)
every Friday's weekly summary

### `activity` — ⋯ עוד → 📜 הפעילות שלי (My activity)
my full activity timeline: filters, search, monthly summary, CSV/Excel
- `activity.filters` **סינון וחיפוש** (Filter and search, expander): dates, type, ticker, source, search  
  path: ⋯ עוד → 📜 הפעילות שלי → סינון וחיפוש
- `activity.download` **הפעילות שלי** (My activity, buttons): CSV / Excel of the filtered list  
  path: ⋯ עוד → 📜 הפעילות שלי → הפעילות שלי
- `activity.monthly` **סיכום חודשי** (Monthly summary, expander): per month: deposits, withdrawals, trades, alerts, imports  
  path: ⋯ עוד → 📜 הפעילות שלי → סיכום חודשי

### `track` — ⋯ עוד → 🏆 הצלחה (Track record)
hit rate over time, what the app learned, paper portfolio, App vs Claude vs benchmark, Claude's journal
- `track.vs` **האפליקציה מול Claude מול {b}** (App vs Claude vs {b}, cards): App vs Claude vs benchmark per horizon  
  path: ⋯ עוד → 🏆 הצלחה → האפליקציה מול Claude מול {b}
- `track.journal` **📓 היומן של Claude** (📓 Claude's journal, table): every Claude pick and its results  
  path: ⋯ עוד → 🏆 הצלחה → 📓 היומן של Claude

### `smart` — ⋯ עוד → 💰 כסף חכם (Smart money)
insider buys, buybacks, big funds (13F)

### `sectors` — ⋯ עוד → 🌍 סקטורים (Sectors)
which sectors are hot or cold

### `history` — ⋯ עוד → 📜 היסטוריה (History)
similar market periods since 1990 and event base rates

### `advanced` — ⋯ עוד → ⚙️ מתקדם (Advanced)
the original English tables: overview, research, track record, charts, backtest, log, connections

### `connections` — ⋯ עוד → 🔌 חיבורים (Connections)
is everything connected: data, GitHub run, public feed, data check, Claude picks/report today

## Common tasks, step by step
### Import a broker file
1. 💼 התיק שלי → 📥 ייבוא קובץ מהברוקר
2. choose the account, Browse files (CSV/XLSX/XLS)
3. check 'התאמת עמודות' (🔴 = confirm the column), label unknown codes once
4. read the preview: new vs duplicates, holdings, differences, cash warnings
5. choose: למזג (merge) if you typed trades after the file's last date; להשתמש בקובץ (use file) if the file is complete and newer than the app; להשאיר את הקיים (keep) to save only the transactions
6. אשר ושמור

### Add a deposit
1. 💼 התיק שלי → ✏️ עריכה → הפקדות
2. add a row: date, account, amount (> 0)
3. שמור שינויים

### Add a trade
1. 💼 התיק שלי → ➕ עסקה חדשה
2. buy/sell, account, ticker, shares, price, date
3. שמור עסקה

### Fix wrong holdings
1. first try 💼 → 📥 import the latest activity file (merge)
2. or 💼 → ✏️ עריכה → החזקות: change units/avg cost (marked manual) → שמור שינויים
3. mistake? ↩️ היסטוריה → בטל את השינוי האחרון

### Change the benchmark
1. 🎯 כוונון → מול מה משווים → choose (saved at once)

### Add a watchlist alert
1. 🎯 כוונון → 🔔 התראות משלך
2. ticker, מתי להתריע, value (price or %), דחוף?
3. הוסף התראה

### Write an instruction to Claude
1. 🎯 כוונון → 🧠 הנחיה ל-Claude
2. type it (no personal details: it is public)
3. שלח ל-Claude; the answer appears there after the next 8:30 collection

### Download a backup
1. ⋯ עוד (or 💼) → 📦 הורד את הנתונים שלי (zip)
2. weekly backups: GitHub → Releases

### Read the morning report
1. 🏠 היום → 🧠 Claude אומר → לדוח המלא
2. or ⋯ עוד → 📰 דוח הבוקר → choose the date

## What the colors and warnings mean

| Sign | Meaning | What to do |
|---|---|---|
| 🟢 / green | all good (traffic light, data check pass, connection ok) | nothing |
| 🟡 / yellow | close to a rule (e.g. TQQQ within 2% of the $570 floor) or a data warning | watch; no action needed yet |
| 🔴 / red | a rule is broken, the signal changed, or a check failed | read the sentence on 🏠; decide (sell / add money) per your rules |
| ⚠️ לא מאומת / unverified | today's QQQ/TQQQ prices didn't match a second source | don't act on the TQQQ signal until the next check |
| ⚠️ in the import preview | differences with the app, negative cash (missing deposit), or an option that overwrites data | read it before אשר ושמור |
| ⏳ ממתין / waiting | an instruction Claude hasn't answered yet | wait for the next morning report |
| n/a | data missing or older than 200 days (fundamentals) — never guessed | nothing |
