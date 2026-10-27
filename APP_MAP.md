# App map

Every screen of the app, in order, with the exact Hebrew labels (English in brackets), what each element does and the path to it. Stable ids (`page` / `page.section`) let a chat say navigate("portfolio", "import").

## Bottom tabs
- `today` **🏠 היום** (Today): one phone screen, live: a top line '✅ הכל מסונכרן · עודכן <time> שעון מיאמי' (or what is missing) + market open/closed + ⚙️ + 🔄 refresh now; 3 cards: my money in ALL accounts (total, today $/%, one line per broker: Robinhood, Fidelity - no breakdown; up to 2 📌 lines of what touches my holdings), the analyst's forecast (today / this week, the last scored day, the record; the market sentence folded), Claude's virtual portfolio (value, return, TODAY'S ORDERS or 'no orders today', the day's reason; tap -> 🤖). Refreshes itself every 60 s while the market is open (9:30-16:00 Miami time)
- `stock` **📊 מניה** (A stock): any stock: score + plain sentence, fundamentals, chart, factor bars, news vs Claude, insiders, headlines; 💰 what it is worth: the nightly model (or build one now) with its A/B/C grade, what the price implies, the football field and the Excel file
- `claude_portfolio` **🤖 התיק של Claude** (Claude's portfolio): the VIRTUAL $10,000 portfolio Claude trades once a day on its own judgment: value vs benchmark and QQQ, open positions with stop/target/thesis/source, closed trades with lessons, results by idea source, journal; your controls (close, block, pause, idea)
- `chat` **💬 Claude** (Claude): the in-app Claude analyst (a bottom tab; opens with a 3-line 'what is happening now' from the live context): explains screens, numbers and choices, opens screens, proposes changes you approve; can read the app's code and propose a code fix (a diff card; 'אשר ופתח PR' opens a GitHub Pull Request you merge yourself)

## Other screens (the 🤖 tab's buttons; 🏠 → ⚙️ for my portfolio)
- `portfolio` **✏️ ניהול התיק** (Manage my money): (⚙️ → my portfolio → edit) FIX MY PORTFOLIO: everything comes from the broker sync; this page only fixes what is wrong. Sync status + 🔄 sync now, one-tap fixes, then 'מה צריך לתקן?' with 6 choices (record a trade, a missing/wrong deposit, a wrong holding, import a broker file, accounts, undo the last change) -> that one form. Totals are on 🏠
- `more` **⚙️ מתקדם** (Advanced): ⚙️ Advanced (from 🏠's ⚙️): my portfolio (edit · log · connections, a button row on top of each) + language + reload + download my data + copy for Claude
- `report` **📰 דוח הבוקר** (Morning report): morning Claude's full report, archive by date, that day's picks, Open in Google Drive
- `activity` **📜 הפעילות שלי** (My activity): (⚙️ → my portfolio → log) what happened, newest first: by default only what matters (trades, deposits, Claude's decisions, problems, my edits); 'show everything' adds notifications and automatic steps; search + CSV/Excel folded, monthly summary
- `connections` **🔌 חיבורים** (Connections): (⚙️ → my portfolio → connections) is everything that feeds the app working, in 4 plain lines: broker sync, this morning's Claude report, the evening run, the self-check (🟢/🟡/🔴/⚪); technical details folded
- `questions` **📝 השאלות היומיות לאנליסט** (The analyst's daily questions): the analyst's daily questions: this morning's answers (view + confidence + tickers) next to the previous day's, 'view changed' marks, and how its ticker views did vs QQQ after 5 days

## Screens in detail
### `today` — 🏠 היום (Today)
one phone screen, live: a top line '✅ הכל מסונכרן · עודכן <time> שעון מיאמי' (or what is missing) + market open/closed + ⚙️ + 🔄 refresh now; 3 cards: my money in ALL accounts (total, today $/%, one line per broker: Robinhood, Fidelity - no breakdown; up to 2 📌 lines of what touches my holdings), the analyst's forecast (today / this week, the last scored day, the record; the market sentence folded), Claude's virtual portfolio (value, return, TODAY'S ORDERS or 'no orders today', the day's reason; tap -> 🤖). Refreshes itself every 60 s while the market is open (9:30-16:00 Miami time)
- `today.money` **💰 הכסף שלי · כל החשבונות** (💰 My money · all accounts, card): all accounts: total, today $/%, one line per broker (Robinhood, Fidelity); up to 2 📌 lines of what touches my holdings (earnings soon, a big report tomorrow)  
  path: 🏠 היום → 💰 הכסף שלי · כל החשבונות
- `today.forecast` **🔮 התחזית של האנליסט** (🔮 The analyst's forecast, card): the analyst's forecast for SPY / QQQ today and this week, the last scored day, the record; the market sentence folded  
  path: 🏠 היום → 🔮 התחזית של האנליסט
- `today.claude` **🤖 התיק של Claude** (🤖 Claude's portfolio, card): Claude's virtual portfolio: value, return, today's orders (or 'no orders today' / waiting for the 10:15 decision) and the day's reason; tap -> 🤖  
  path: 🏠 היום → 🤖 התיק של Claude
- `today.settings` **מתקדם** (Advanced, button): ⚙️ -> my portfolio: edit / log / connections  
  path: 🏠 היום → מתקדם
- `today.refresh` **רענן עכשיו: מחירים חדשים ובקשת סנכרון מהברוקר** (Refresh now: new prices and a broker sync request, button): 🔄 new prices now + ask the broker sync to run (2-3 minutes)  
  path: 🏠 היום → רענן עכשיו: מחירים חדשים ובקשת סנכרון מהברוקר

### `portfolio` — 🏠 → ⚙️ → ✏️ ניהול התיק (Manage my money)
(⚙️ → my portfolio → edit) FIX MY PORTFOLIO: everything comes from the broker sync; this page only fixes what is wrong. Sync status + 🔄 sync now, one-tap fixes, then 'מה צריך לתקן?' with 6 choices (record a trade, a missing/wrong deposit, a wrong holding, import a broker file, accounts, undo the last change) -> that one form. Totals are on 🏠
- `portfolio.sync` **סנכרן עכשיו** (Sync now, button): 'סונכרן עם Robinhood <time>' (amber = old or failed) + 🔄 סנכרן עכשיו: reads the brokers through SnapTrade (read-only) in ~2-3 minutes  
  path: 🏠 → ⚙️ → ✏️ ניהול התיק → סנכרן עכשיו
- `portfolio.issues` **כנראה חסרה הפקדה** (A deposit is probably missing, card): issues with a one-tap fix: add the missing deposit (pre-filled, you confirm) or ignore  
  path: 🏠 → ⚙️ → ✏️ ניהול התיק → כנראה חסרה הפקדה
- `portfolio.trade` **📝 לרשום קנייה או מכירה** (📝 Record a buy or a sell, choice): record a buy/sell the sync hasn't seen: account, ticker, shares, price, date -> save trade  
  path: 🏠 → ⚙️ → ✏️ ניהול התיק → 📝 לרשום קנייה או מכירה
- `portfolio.deposits` **💵 הפקדה או משיכה חסרה / שגויה** (💵 A deposit or withdrawal is missing / wrong, choice): table of deposits/withdrawals (amount < 0 = withdrawal) -> save changes; keeps the return from counting a deposit as profit  
  path: 🏠 → ⚙️ → ✏️ ניהול התיק → 💵 הפקדה או משיכה חסרה / שגויה
- `portfolio.holdings` **📦 כמות או מחיר קנייה של מניה לא נכונים** (📦 A holding's shares or buy price is wrong, choice): table of holdings: units / avg cost (rows you change are marked manual; the next broker sync is still the truth) -> save changes  
  path: 🏠 → ⚙️ → ✏️ ניהול התיק → 📦 כמות או מחיר קנייה של מניה לא נכונים
- `portfolio.import` **📥 לייבא קובץ מהברוקר** (📥 Import a file from the broker, choice): upload a broker CSV/XLSX/XLS -> column matching -> preview -> merge / use file / keep -> אשר ושמור  
  path: 🏠 → ⚙️ → ✏️ ניהול התיק → 📥 לייבא קובץ מהברוקר
- `portfolio.accounts` **🏦 להוסיף או לשנות חשבון** (🏦 Add or rename an account, choice): table of accounts -> save changes  
  path: 🏠 → ⚙️ → ✏️ ניהול התיק → 🏦 להוסיף או לשנות חשבון
- `portfolio.undo` **↩️ לבטל את השינוי האחרון** (↩️ Undo the last change, choice): undo the last portfolio change + the change history  
  path: 🏠 → ⚙️ → ✏️ ניהול התיק → ↩️ לבטל את השינוי האחרון
- `portfolio.download` **הורד את הנתונים שלי (zip)** (Download my data (zip), button): download every data file as a zip  
  path: 🏠 → ⚙️ → ✏️ ניהול התיק → הורד את הנתונים שלי (zip)

### `more` — 🏠 היום → ⚙️ (Advanced)
⚙️ Advanced (from 🏠's ⚙️): my portfolio (edit · log · connections, a button row on top of each) + language + reload + download my data + copy for Claude
- `more.list` **מתקדם** (Advanced, list): every other screen, in groups  
  path: 🏠 היום → ⚙️ → מתקדם
- `more.language` **שפה** (Language, radio): עברית / English  
  path: 🏠 היום → ⚙️ → שפה
- `more.reload` **רענון נתונים** (Reload data, button): reload the data  
  path: 🏠 היום → ⚙️ → רענון נתונים
- `more.download` **הורד את הנתונים שלי (zip)** (Download my data (zip), button): download my data (zip)  
  path: 🏠 היום → ⚙️ → הורד את הנתונים שלי (zip)

### `stock` — 📊 מניה (A stock)
any stock: score + plain sentence, fundamentals, chart, factor bars, news vs Claude, insiders, headlines; 💰 what it is worth: the nightly model (or build one now) with its A/B/C grade, what the price implies, the football field and the Excel file
- `stock.pick` **בחר מניה** (Pick a stock, select): choose any stock (🔥 hot, 🧊 cold)  
  path: 📊 מניה → בחר מניה
- `stock.fundamentals` **📑 דוחות כספיים** (📑 Fundamentals, card): revenue, margins, debt, P/E (n/a = missing)  
  path: 📊 מניה → 📑 דוחות כספיים
- `stock.breakdown` **ממה מורכב הציון** (What the score is made of, card): each factor bar with a one-line meaning; app news vs Claude rating  
  path: 📊 מניה → ממה מורכב הציון

### `report` — 🤖 התיק של Claude → 📰 דוח הבוקר (Morning report)
morning Claude's full report, archive by date, that day's picks, Open in Google Drive
- `report.date` **איזה דוח להציג** (Which report, select): which day's report  
  path: 🤖 התיק של Claude → 📰 דוח הבוקר → איזה דוח להציג
- `report.drive` **פתח ב-Google Drive** (Open in Google Drive, link): Google Drive search  
  path: 🤖 התיק של Claude → 📰 דוח הבוקר → פתח ב-Google Drive
- `report.picks` **הבחירות של Claude ליום הזה** (Claude's picks for this day, table): that day's structured picks  
  path: 🤖 התיק של Claude → 📰 דוח הבוקר → הבחירות של Claude ליום הזה

### `activity` — 🏠 → ⚙️ → 📜 הפעילות שלי (My activity)
(⚙️ → my portfolio → log) what happened, newest first: by default only what matters (trades, deposits, Claude's decisions, problems, my edits); 'show everything' adds notifications and automatic steps; search + CSV/Excel folded, monthly summary
- `activity.all` **הצג הכל (גם התראות ופעולות אוטומטיות)** (Show everything (also notifications and automatic steps), toggle): off = only what matters; on = also notifications and automatic steps  
  path: 🏠 → ⚙️ → 📜 הפעילות שלי → הצג הכל (גם התראות ופעולות אוטומטיות)
- `activity.filters` **סינון וחיפוש** (Filter and search, expander): dates, type, ticker, source, search + CSV / Excel download  
  path: 🏠 → ⚙️ → 📜 הפעילות שלי → סינון וחיפוש
- `activity.monthly` **סיכום חודשי** (Monthly summary, expander): per month: deposits, withdrawals, trades, alerts, imports  
  path: 🏠 → ⚙️ → 📜 הפעילות שלי → סיכום חודשי

### `connections` — 🏠 → ⚙️ → 🔌 חיבורים (Connections)
(⚙️ → my portfolio → connections) is everything that feeds the app working, in 4 plain lines: broker sync, this morning's Claude report, the evening run, the self-check (🟢/🟡/🔴/⚪); technical details folded

### `questions` — 🤖 התיק של Claude → 📝 השאלות היומיות לאנליסט (The analyst's daily questions)
the analyst's daily questions: this morning's answers (view + confidence + tickers) next to the previous day's, 'view changed' marks, and how its ticker views did vs QQQ after 5 days

### `claude_portfolio` — 🤖 התיק של Claude (Claude's portfolio)
the VIRTUAL $10,000 portfolio Claude trades once a day on its own judgment: value vs benchmark and QQQ, open positions with stop/target/thesis/source, closed trades with lessons, results by idea source, journal; your controls (close, block, pause, idea)
- `claude_portfolio.decision` **ההחלטה של {d}** (Decision of {d}, card): today's decision: what Claude did and why, what it watches tomorrow, the cost  
  path: 🤖 התיק של Claude → ההחלטה של {d}
- `claude_portfolio.positions` **פוזיציות פתוחות** (Open positions, cards): each open position + ✖️ סגור (close at the next price) and 🚫 חסום  
  path: 🤖 התיק של Claude → פוזיציות פתוחות
- `claude_portfolio.closed` **עסקאות סגורות ({n}) ומה Claude למד** (Closed trades ({n}) and what Claude learned, expander): closed trades, ✓/✗ vs the benchmark, Claude's lesson for each  
  path: 🤖 התיק של Claude → עסקאות סגורות ({n}) ומה Claude למד
- `claude_portfolio.sources` **תוצאות לפי מקור הרעיון** (Results by idea source, table): hit rate and average return by idea source  
  path: 🤖 התיק של Claude → תוצאות לפי מקור הרעיון
- `claude_portfolio.journal` **יומן הלמידה** (Learning journal, expander): the learning journal + weekly lessons  
  path: 🤖 התיק של Claude → יומן הלמידה
- `claude_portfolio.controls` **השליטה שלך** (Your controls, expander): pause/resume, unblock, suggest an idea; the safety rails  
  path: 🤖 התיק של Claude → השליטה שלך

### `chat` — 💬 Claude (Claude)
the in-app Claude analyst (a bottom tab; opens with a 3-line 'what is happening now' from the live context): explains screens, numbers and choices, opens screens, proposes changes you approve; can read the app's code and propose a code fix (a diff card; 'אשר ופתח PR' opens a GitHub Pull Request you merge yourself)
- `chat.ask` **שאל אותי משהו… (אפשר לצרף צילום מסך)** (Ask me anything… (you can attach a screenshot), input): type a question; 📎 attach a screenshot (it is resized and sent with the screen data)  
  path: 💬 Claude → שאל אותי משהו… (אפשר לצרף צילום מסך)
- `chat.review` **סקירה** (Review, button): 📋 the weekly review: what I did, decisions vs my rules, data problems, 3 ideas  
  path: 💬 Claude → סקירה
- `chat.clear` **נקה שיחה** (Clear chat, button): start a fresh conversation (the history file is kept)  
  path: 💬 Claude → נקה שיחה
- `chat.hard` **שאלה קשה (מודל חזק ויקר יותר)** (Hard question (stronger, pricier model), toggle): use the stronger, pricier model for one hard question  
  path: 💬 Claude → שאלה קשה (מודל חזק ויקר יותר)
- `chat.approve` **אשר** (Approve, button): on a ✋ proposal card: apply the change (nothing changes without it)  
  path: 💬 Claude → אשר
- `chat.code_fix` **אשר ופתח PR** (Approve and open PR, button): on a 🛠️ code-fix card: see the diff, then open a GitHub Pull Request (never merged by the app)  
  path: 💬 Claude → אשר ופתח PR

## Common tasks, step by step
### Import a broker file
1. ⚙️ → התיק שלי → עריכה → מה צריך לתקן? → 📥 לייבא קובץ מהברוקר
2. choose the account, Browse files (CSV/XLSX/XLS)
3. check 'התאמת עמודות' (🔴 = confirm the column), label unknown codes once
4. read the preview: new vs duplicates, holdings, differences, cash warnings
5. choose: למזג (merge) if you typed trades after the file's last date; להשתמש בקובץ (use file) if the file is complete and newer than the app; להשאיר את הקיים (keep) to save only the transactions
6. אשר ושמור

### Add a deposit
1. ⚙️ → התיק שלי → עריכה → 💵 הפקדה או משיכה חסרה / שגויה
2. add a row: date, account, amount (> 0)
3. שמור שינויים

### Add a trade
1. ⚙️ → התיק שלי → עריכה → 📝 לרשום קנייה או מכירה
2. buy/sell, account, ticker, shares, price, date
3. שמור עסקה

### Fix wrong holdings
1. first 🔄 sync now (the broker is the truth for share counts); still wrong: עריכה → 📥 import the latest activity file (merge)
2. or עריכה → 📦 כמות או מחיר קנייה של מניה לא נכונים: change units/avg cost (marked manual) → שמור שינויים
3. mistake? עריכה → ↩️ לבטל את השינוי האחרון

### Sync with Robinhood now
1. 🏠 היום → 🔄 (top right): new prices now + a broker sync request
2. wait 2-3 minutes
3. it also runs by itself at 06:30, 12:30 and 16:15 and 17:30 Miami time on trading days, and when you open the app with share counts older than 60 minutes

### Check that everything works
1. ⚙️ → התיק שלי → חיבורים: 4 lines (broker sync, morning report, evening run, self-check); 🟢 OK · 🟡 worth a look · 🔴 needs action
2. red broker sync -> 🔄 sync now, then reconnect (below) if it still fails

### See what happened / when
1. ⚙️ → התיק שלי → יומן: newest first, only what matters
2. turn on 'הצג הכל' for notifications and automatic steps; 🔎 to search or download

### Reconnect Robinhood (sync failed / expired)
1. snaptrade.com → Dashboard → Connections → Robinhood → Reconnect (log in at Robinhood, read-only)
2. then 🏠 → 🔄

### Change the benchmark / add a price alert / write an instruction to the morning Claude
1. ask in 💬 Claude (the 🎯 tune screen was removed Oct 27 2026): it proposes the change (set_benchmark / add_alert / add_instruction) and applies it after you press אשר

### Download a backup
1. 🏠 → ⚙️ מתקדם → 📦 הורד את הנתונים שלי (zip)
2. weekly backups: GitHub → Releases

### Read the morning report
1. 🤖 התיק של Claude → 📰 דוח הבוקר → choose the date

## What the colors and warnings mean

| Sign | Meaning | What to do |
|---|---|---|
| 🟢 / green | all good (traffic light, data check pass, connection ok) | nothing |
| 🟡 / yellow | close to a rule (e.g. TQQQ less than 3% above its 200-day average) or a data warning | watch; no action needed yet |
| 🔴 / red | a rule is broken, the signal changed, or a check failed | read the sentence on 🏠; decide (sell / add money) per your rules |
| ⚠️ לא מאומת / unverified | today's QQQ/TQQQ prices didn't match a second source | don't act on the TQQQ signal until the next check |
| ⚠️ in the import preview | differences with the app, negative cash (missing deposit), or an option that overwrites data | read it before אשר ושמור |
| ⏳ ממתין / waiting | an instruction Claude hasn't answered yet | wait for the next morning report |
| n/a | data missing or older than 200 days (fundamentals) — never guessed | nothing |
| 🔄 amber 'סונכרן לאחרונה' | the Robinhood sync failed or is older than 36 hours; the last good data is shown | 🏠 → 🔄; if it says expired, reconnect in SnapTrade |
