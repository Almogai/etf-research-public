# App map

Every screen of the app, in order, with the exact Hebrew labels (English in brackets), what each element does and the path to it. Stable ids (`page` / `page.section`) let a chat say navigate("portfolio", "import").

## Bottom tabs
- `today` **🏠 היום** (Today): one phone screen, live: a top line '✅ הכל מסונכרן · עודכן <time> שעון מיאמי' (or what is missing) + market open/closed + 🔄 refresh now; 4 cards: my money in ALL accounts (live total, today $/% , since the start, TQQQ vs its 200-day line green/amber/red, share counts as of the last broker sync), Claude's picks (price, today, since the pick, status, stop→target bar, up/down vs SPY), the market in 2-3 Hebrew sentences, what to do (only actions). Refreshes itself every 60 s while the market is open (9:30-16:00 Miami time)
- `money` **💼 התיק** (Portfolio): every holding in every account in one table (live prices × broker share counts), total/today/since the start, Claude's VIRTUAL portfolio vs QQQ and SPY, and the ⚙️ Advanced button
- `chat` **💬 Claude** (Claude): the in-app Claude analyst (a bottom tab; opens with a 3-line 'what is happening now' from the live context): explains screens, numbers and choices, opens screens, proposes changes you approve; can read the app's code and propose a code fix (a diff card; 'אשר ופתח PR' opens a GitHub Pull Request you merge yourself)

## Under 💼 → ⚙️ מתקדם (Advanced), in order
- `status` **📋 סטטוס מלא** (Full status): what Today used to show: pre-open checklist, traffic light + TQQQ/200-day sentence, my money, what changed since yesterday, Claude says, today's top 5 chips
- `top5` **🔥 Top 5** (Top 5): the virtual $10,000 test of the daily top 5 (App / Claude), open and closed positions, my watchlist
- `portfolio` **✏️ ניהול התיק** (Manage my money): (under ⚙️ Advanced) net worth, a card per holding, allocation, broker import, editing (trade, deposits, holdings, accounts, undo), TQQQ rules
- `tune` **🎯 כוונון** (Tune): benchmark, screener preferences + preview, my own alerts, instructions to Claude, a link to the live chat
- `more` **⚙️ מתקדם** (Advanced): ⚙️ Advanced (from 💼): every other screen in groups + language + reload + download my data + copy for Claude
- `overview` **📋 סקירה מלאה** (Full overview): the previous home page: summary, mood, hot 5 cards, stay-away 5
- `stock` **📊 מניה** (Stock details): any stock: score + plain sentence, fundamentals, chart, factor bars, news vs Claude, insiders, headlines
- `report` **📰 דוח הבוקר** (Morning report): morning Claude's full report, archive by date, that day's picks, Open in Google Drive
- `weekly` **📅 סיכום שבועי** (Weekly summary): every Friday's weekly summary
- `activity` **📜 הפעילות שלי** (My activity): my full activity timeline: filters, search, monthly summary, CSV/Excel
- `track` **🏆 הצלחה** (Track record): hit rate over time, what the app learned, paper portfolio, App vs Claude vs benchmark, Claude's journal
- `smart` **💰 כסף חכם** (Smart money): insider buys, buybacks, big funds (13F)
- `sectors` **🌍 סקטורים** (Sectors): which sectors are hot or cold
- `history` **📜 היסטוריה** (History): similar market periods since 1990 and event base rates
- `advanced` **🗂️ טבלאות באנגלית** (English tables): the original English tables: overview, research, track record, charts, backtest, log, connections
- `connections` **🔌 חיבורים** (Connections): is everything connected: data, GitHub run, public feed, data check, Claude picks/report today
- `claude_portfolio` **🤖 תיק Claude (וירטואלי)** (Claude portfolio (virtual)): the VIRTUAL $10,000 portfolio Claude trades once a day on its own judgment: value vs benchmark and QQQ, open positions with stop/target/thesis/source, closed trades with lessons, results by idea source, journal; your controls (close, block, pause, idea)
- `live` **🎯 הבחירות של Claude — חי** (Claude's picks — live): morning Claude's top 5 right now: source (ntfy message, the app's archive or the Google Drive backup), average since the pick vs QQQ, a card per pick (price, today, since the pick, status: in/below/above the buy zone, stop hit, target hit, a bar from stop to target), today's 5-minute chart (refreshes every minute while the market is open), sync check vs the app's top 5

## Screens in detail
### `today` — 🏠 היום (Today)
one phone screen, live: a top line '✅ הכל מסונכרן · עודכן <time> שעון מיאמי' (or what is missing) + market open/closed + 🔄 refresh now; 4 cards: my money in ALL accounts (live total, today $/% , since the start, TQQQ vs its 200-day line green/amber/red, share counts as of the last broker sync), Claude's picks (price, today, since the pick, status, stop→target bar, up/down vs SPY), the market in 2-3 Hebrew sentences, what to do (only actions). Refreshes itself every 60 s while the market is open (9:30-16:00 Miami time)
- `today.money` **💰 הכסף שלי** (💰 My money, card): total, today, since the start; one line TQQQ vs its 200-day average: green OK / amber less than 3% above / red below = exit  
  path: 🏠 היום → 💰 הכסף שלי
- `today.picks` **🧠 הבחירות של Claude** (🧠 Claude's picks, card): Claude's picks: price, % today, % since the pick, a bar from stop to target; how many up/down vs SPY; tap -> 📊 stock  
  path: 🏠 היום → 🧠 הבחירות של Claude
- `today.market` **🌎 השוק במשפט** (🌎 The market in a sentence, card): 2-3 lines from this morning's report; 'Full report' opens 📰  
  path: 🏠 היום → 🌎 השוק במשפט
- `today.todo` **✅ מה לעשות** (✅ What to do, card): only actions that need me (rule says exit, signal changed, reconnect Robinhood, a held pick hit stop/target); otherwise 'אין מה לעשות היום'  
  path: 🏠 היום → ✅ מה לעשות
- `today.refresh` **רענן עכשיו: מחירים חדשים ובקשת סנכרון מהברוקר** (Refresh now: new prices and a broker sync request, button): 🔄 new prices now + ask the broker sync to run (2-3 minutes)  
  path: 🏠 היום → רענן עכשיו: מחירים חדשים ובקשת סנכרון מהברוקר

### `money` — 💼 התיק (Portfolio)
every holding in every account in one table (live prices × broker share counts), total/today/since the start, Claude's VIRTUAL portfolio vs QQQ and SPY, and the ⚙️ Advanced button
- `money.total` **💰 הכסף שלי · כל החשבונות** (💰 My money · all accounts, card): all accounts: total, today, money in, since the start, share counts as of  
  path: 💼 התיק → 💰 הכסף שלי · כל החשבונות
- `money.holdings` **מניה** (Holding, table): every holding per account: units, today %, value  
  path: 💼 התיק → מניה
- `money.virtual` **התיק הווירטואלי של Claude (כסף לא אמיתי)** (Claude's virtual portfolio (not real money), card): Claude's virtual $10,000: value, return, vs QQQ and SPY; link to its screen  
  path: 💼 התיק → התיק הווירטואלי של Claude (כסף לא אמיתי)
- `money.advanced` **מתקדם: סורק, בדיקת עבר, הגדרות, יומנים ועוד** (Advanced: screener, backtest, settings, logs and more, link): ⚙️ Advanced: every other screen  
  path: 💼 התיק → מתקדם: סורק, בדיקת עבר, הגדרות, יומנים ועוד

### `status` — 💼 התיק → ⚙️ מתקדם → 📋 סטטוס מלא (Full status)
what Today used to show: pre-open checklist, traffic light + TQQQ/200-day sentence, my money, what changed since yesterday, Claude says, today's top 5 chips
- `status.status` **הכול בסדר** (All good, card): traffic light: green ok / yellow close to a rule / red rule broken or signal changed  
  path: 💼 התיק → ⚙️ מתקדם → 📋 סטטוס מלא → הכול בסדר
- `status.money` **שווי החשבון** (Account value, card): account value, today's change, profit vs deposits  
  path: 💼 התיק → ⚙️ מתקדם → 📋 סטטוס מלא → שווי החשבון
- `status.changed` **🔄 מה השתנה מאתמול** (🔄 What changed since yesterday, card): up to 5 bullets of what changed since yesterday  
  path: 💼 התיק → ⚙️ מתקדם → 📋 סטטוס מלא → 🔄 מה השתנה מאתמול
- `status.claude` **🧠 Claude אומר** (🧠 Claude says, card): 3 lines from the morning report; 'Full report' opens 📰  
  path: 💼 התיק → ⚙️ מתקדם → 📋 סטטוס מלא → 🧠 Claude אומר
- `status.top5` **ה-Top 5 של היום** (Today's top 5, chips): today's top 5 tickers; tap -> 🔥 Top 5  
  path: 💼 התיק → ⚙️ מתקדם → 📋 סטטוס מלא → ה-Top 5 של היום

### `top5` — 💼 התיק → ⚙️ מתקדם → 🔥 Top 5 (Top 5)
the virtual $10,000 test of the daily top 5 (App / Claude), open and closed positions, my watchlist
- `top5.who` **האפליקציה** (App, toggle): App / Claude: whose picks the test shows  
  path: 💼 התיק → ⚙️ מתקדם → 🔥 Top 5 → האפליקציה
- `top5.value` **שווי התיק הווירטואלי** (Virtual portfolio value, card): virtual value, return, vs the benchmark  
  path: 💼 התיק → ⚙️ מתקדם → 🔥 Top 5 → שווי התיק הווירטואלי
- `top5.open` **פוזיציות פתוחות** (Open positions, list): open positions by buy day (day x/5); tap a ticker -> stock details  
  path: 💼 התיק → ⚙️ מתקדם → 🔥 Top 5 → פוזיציות פתוחות
- `top5.closed` **עסקאות שנסגרו** (Closed trades, list): closed trades with ✓/✗ vs the benchmark  
  path: 💼 התיק → ⚙️ מתקדם → 🔥 Top 5 → עסקאות שנסגרו
- `top5.watchlist` **👀 רשימת המעקב שלי** (👀 My watchlist, list): my watchlist with today's alerts  
  path: 💼 התיק → ⚙️ מתקדם → 🔥 Top 5 → 👀 רשימת המעקב שלי

### `portfolio` — 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק (Manage my money)
(under ⚙️ Advanced) net worth, a card per holding, allocation, broker import, editing (trade, deposits, holdings, accounts, undo), TQQQ rules
- `portfolio.sync` **סנכרן עכשיו** (Sync now, button): 'סונכרן עם Robinhood <time>' (amber = old or failed) + 🔄 סנכרן עכשיו: reads Robinhood through SnapTrade (read-only) in ~2-3 minutes  
  path: 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק → סנכרן עכשיו
- `portfolio.issues` **כנראה חסרה הפקדה** (A deposit is probably missing, card): issues with a one-tap fix: add the missing deposit (pre-filled, you confirm) or ignore  
  path: 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק → כנראה חסרה הפקדה
- `portfolio.totals` **שווי כולל** (Net worth, card): net worth, money in, profit, time-weighted return  
  path: 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק → שווי כולל
- `portfolio.holdings` **החזקות** (Holdings, cards): a card per holding with value and P&L  
  path: 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק → החזקות
- `portfolio.allocation` **חלוקה וחשיפה** (Allocation & exposure, expander): shares by ticker/type/sector/account, exposure, concentration limit slider  
  path: 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק → חלוקה וחשיפה
- `portfolio.import` **ייבוא קובץ מהברוקר** (Import from your broker, expander): upload CSV/XLSX/XLS -> column matching -> label unknown codes -> preview -> choose merge / use file / keep -> אשר ושמור  
  path: 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק → ייבוא קובץ מהברוקר
- `portfolio.trade` **עסקה חדשה** (New trade, tab): form: buy/sell, account, ticker, shares, price, date, type -> save trade  
  path: 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק → עסקה חדשה
- `portfolio.deposits` **הפקדות** (Deposits, tab): table of deposits/withdrawals (amount < 0 = withdrawal) -> save changes  
  path: 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק → הפקדות
- `portfolio.holdings_edit` **החזקות** (Holdings, tab): table of holdings (edits are marked manual) -> save changes  
  path: 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק → החזקות
- `portfolio.accounts` **חשבונות** (Accounts, tab): table of accounts -> save changes  
  path: 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק → חשבונות
- `portfolio.history` **היסטוריה** (History, tab): undo the last change + the change history  
  path: 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק → היסטוריה
- `portfolio.charts` **חלוקה ושווי לאורך זמן** (Allocation and value over time, expander): pies and value over time  
  path: 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק → חלוקה ושווי לאורך זמן
- `portfolio.rules` **TQQQ והכללים** (TQQQ and the rules, expander): TQQQ positions, exposure gauge, the 200-day exit rule and rules A-E  
  path: 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק → TQQQ והכללים
- `portfolio.download` **הורד את הנתונים שלי (zip)** (Download my data (zip), button): download every data file as a zip  
  path: 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק → הורד את הנתונים שלי (zip)

### `tune` — 💼 התיק → ⚙️ מתקדם → 🎯 כוונון (Tune)
benchmark, screener preferences + preview, my own alerts, instructions to Claude, a link to the live chat
- `tune.benchmark` **מול מה משווים** (What we compare with, select): QQQ / SPY / cash / sector ETF: every 'vs' number uses it (saved at once)  
  path: 💼 התיק → ⚙️ מתקדם → 🎯 כוונון → מול מה משווים
- `tune.preferences` **ההעדפות שלך** (Your preferences, form): focus/avoid sectors, risk, horizon, picks per day, watchlist, exclude -> save; preview of today's top  
  path: 💼 התיק → ⚙️ מתקדם → 🎯 כוונון → ההעדפות שלך
- `tune.alerts` **🔔 התראות משלך** (🔔 Your own alerts, form): ticker + rule (above/below/move/50-200 cross/insider) + urgent -> add; ✕ deletes  
  path: 💼 התיק → ⚙️ מתקדם → 🎯 כוונון → 🔔 התראות משלך
- `tune.instructions` **🧠 הנחיה ל-Claude** (🧠 Instructions for Claude, form): text -> send to Claude (public file); answers appear under each item  
  path: 💼 התיק → ⚙️ מתקדם → 🎯 כוונון → 🧠 הנחיה ל-Claude
- `tune.chat` **צ'אט עם Claude** (Chat with Claude, link): opens 💬 the live chat  
  path: 💼 התיק → ⚙️ מתקדם → 🎯 כוונון → צ'אט עם Claude

### `more` — 💼 התיק → ⚙️ מתקדם (Advanced)
⚙️ Advanced (from 💼): every other screen in groups + language + reload + download my data + copy for Claude
- `more.list` **מתקדם** (Advanced, list): every other screen, in groups  
  path: 💼 התיק → ⚙️ מתקדם → מתקדם
- `more.language` **שפה** (Language, radio): עברית / English  
  path: 💼 התיק → ⚙️ מתקדם → שפה
- `more.reload` **רענון נתונים** (Reload data, button): reload the data  
  path: 💼 התיק → ⚙️ מתקדם → רענון נתונים
- `more.download` **הורד את הנתונים שלי (zip)** (Download my data (zip), button): download my data (zip)  
  path: 💼 התיק → ⚙️ מתקדם → הורד את הנתונים שלי (zip)

### `overview` — 💼 התיק → ⚙️ מתקדם → 📋 סקירה מלאה (Full overview)
the previous home page: summary, mood, hot 5 cards, stay-away 5

### `stock` — 💼 התיק → ⚙️ מתקדם → 📊 מניה (Stock details)
any stock: score + plain sentence, fundamentals, chart, factor bars, news vs Claude, insiders, headlines
- `stock.pick` **בחר מניה** (Pick a stock, select): choose any stock (🔥 hot, 🧊 cold)  
  path: 💼 התיק → ⚙️ מתקדם → 📊 מניה → בחר מניה
- `stock.fundamentals` **📑 דוחות כספיים** (📑 Fundamentals, card): revenue, margins, debt, P/E (n/a = missing)  
  path: 💼 התיק → ⚙️ מתקדם → 📊 מניה → 📑 דוחות כספיים
- `stock.breakdown` **ממה מורכב הציון** (What the score is made of, card): each factor bar with a one-line meaning; app news vs Claude rating  
  path: 💼 התיק → ⚙️ מתקדם → 📊 מניה → ממה מורכב הציון

### `report` — 💼 התיק → ⚙️ מתקדם → 📰 דוח הבוקר (Morning report)
morning Claude's full report, archive by date, that day's picks, Open in Google Drive
- `report.date` **איזה דוח להציג** (Which report, select): which day's report  
  path: 💼 התיק → ⚙️ מתקדם → 📰 דוח הבוקר → איזה דוח להציג
- `report.drive` **פתח ב-Google Drive** (Open in Google Drive, link): Google Drive search  
  path: 💼 התיק → ⚙️ מתקדם → 📰 דוח הבוקר → פתח ב-Google Drive
- `report.picks` **הבחירות של Claude ליום הזה** (Claude's picks for this day, table): that day's structured picks  
  path: 💼 התיק → ⚙️ מתקדם → 📰 דוח הבוקר → הבחירות של Claude ליום הזה

### `weekly` — 💼 התיק → ⚙️ מתקדם → 📅 סיכום שבועי (Weekly summary)
every Friday's weekly summary

### `activity` — 💼 התיק → ⚙️ מתקדם → 📜 הפעילות שלי (My activity)
my full activity timeline: filters, search, monthly summary, CSV/Excel
- `activity.filters` **סינון וחיפוש** (Filter and search, expander): dates, type, ticker, source, search  
  path: 💼 התיק → ⚙️ מתקדם → 📜 הפעילות שלי → סינון וחיפוש
- `activity.download` **הפעילות שלי** (My activity, buttons): CSV / Excel of the filtered list  
  path: 💼 התיק → ⚙️ מתקדם → 📜 הפעילות שלי → הפעילות שלי
- `activity.monthly` **סיכום חודשי** (Monthly summary, expander): per month: deposits, withdrawals, trades, alerts, imports  
  path: 💼 התיק → ⚙️ מתקדם → 📜 הפעילות שלי → סיכום חודשי

### `track` — 💼 התיק → ⚙️ מתקדם → 🏆 הצלחה (Track record)
hit rate over time, what the app learned, paper portfolio, App vs Claude vs benchmark, Claude's journal
- `track.vs` **האפליקציה מול Claude מול {b}** (App vs Claude vs {b}, cards): App vs Claude vs benchmark per horizon  
  path: 💼 התיק → ⚙️ מתקדם → 🏆 הצלחה → האפליקציה מול Claude מול {b}
- `track.journal` **📓 היומן של Claude** (📓 Claude's journal, table): every Claude pick and its results  
  path: 💼 התיק → ⚙️ מתקדם → 🏆 הצלחה → 📓 היומן של Claude

### `smart` — 💼 התיק → ⚙️ מתקדם → 💰 כסף חכם (Smart money)
insider buys, buybacks, big funds (13F)

### `sectors` — 💼 התיק → ⚙️ מתקדם → 🌍 סקטורים (Sectors)
which sectors are hot or cold

### `history` — 💼 התיק → ⚙️ מתקדם → 📜 היסטוריה (History)
similar market periods since 1990 and event base rates

### `advanced` — 💼 התיק → ⚙️ מתקדם → 🗂️ טבלאות באנגלית (English tables)
the original English tables: overview, research, track record, charts, backtest, log, connections

### `connections` — 💼 התיק → ⚙️ מתקדם → 🔌 חיבורים (Connections)
is everything connected: data, GitHub run, public feed, data check, Claude picks/report today

### `claude_portfolio` — 💼 התיק → ⚙️ מתקדם → 🤖 תיק Claude (וירטואלי) (Claude portfolio (virtual))
the VIRTUAL $10,000 portfolio Claude trades once a day on its own judgment: value vs benchmark and QQQ, open positions with stop/target/thesis/source, closed trades with lessons, results by idea source, journal; your controls (close, block, pause, idea)
- `claude_portfolio.decision` **ההחלטה של {d}** (Decision of {d}, card): today's decision: what Claude did and why, what it watches tomorrow, the cost  
  path: 💼 התיק → ⚙️ מתקדם → 🤖 תיק Claude (וירטואלי) → ההחלטה של {d}
- `claude_portfolio.positions` **פוזיציות פתוחות** (Open positions, cards): each open position + ✖️ סגור (close at the next price) and 🚫 חסום  
  path: 💼 התיק → ⚙️ מתקדם → 🤖 תיק Claude (וירטואלי) → פוזיציות פתוחות
- `claude_portfolio.closed` **עסקאות סגורות ({n}) ומה Claude למד** (Closed trades ({n}) and what Claude learned, expander): closed trades, ✓/✗ vs the benchmark, Claude's lesson for each  
  path: 💼 התיק → ⚙️ מתקדם → 🤖 תיק Claude (וירטואלי) → עסקאות סגורות ({n}) ומה Claude למד
- `claude_portfolio.sources` **תוצאות לפי מקור הרעיון** (Results by idea source, table): hit rate and average return by idea source  
  path: 💼 התיק → ⚙️ מתקדם → 🤖 תיק Claude (וירטואלי) → תוצאות לפי מקור הרעיון
- `claude_portfolio.journal` **יומן הלמידה** (Learning journal, expander): the learning journal + weekly lessons  
  path: 💼 התיק → ⚙️ מתקדם → 🤖 תיק Claude (וירטואלי) → יומן הלמידה
- `claude_portfolio.controls` **השליטה שלך** (Your controls, expander): pause/resume, unblock, suggest an idea; the safety rails  
  path: 💼 התיק → ⚙️ מתקדם → 🤖 תיק Claude (וירטואלי) → השליטה שלך

### `live` — 💼 התיק → ⚙️ מתקדם → 🎯 הבחירות של Claude — חי (Claude's picks — live)
morning Claude's top 5 right now: source (ntfy message, the app's archive or the Google Drive backup), average since the pick vs QQQ, a card per pick (price, today, since the pick, status: in/below/above the buy zone, stop hit, target hit, a bar from stop to target), today's 5-minute chart (refreshes every minute while the market is open), sync check vs the app's top 5

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
1. 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק → 📥 ייבוא קובץ מהברוקר
2. choose the account, Browse files (CSV/XLSX/XLS)
3. check 'התאמת עמודות' (🔴 = confirm the column), label unknown codes once
4. read the preview: new vs duplicates, holdings, differences, cash warnings
5. choose: למזג (merge) if you typed trades after the file's last date; להשתמש בקובץ (use file) if the file is complete and newer than the app; להשאיר את הקיים (keep) to save only the transactions
6. אשר ושמור

### Add a deposit
1. 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק → הפקדות
2. add a row: date, account, amount (> 0)
3. שמור שינויים

### Add a trade
1. 💼 התיק → ⚙️ מתקדם → ✏️ ניהול התיק → ➕ עסקה חדשה
2. buy/sell, account, ticker, shares, price, date
3. שמור עסקה

### Fix wrong holdings
1. first try ✏️ ניהול התיק → 📥 import the latest activity file (merge)
2. or ✏️ ניהול התיק → החזקות: change units/avg cost (marked manual) → שמור שינויים
3. mistake? ↩️ היסטוריה → בטל את השינוי האחרון

### Sync with Robinhood now
1. 🏠 היום → 🔄 (top right): new prices now + a broker sync request
2. wait 2-3 minutes
3. it also runs by itself at 06:30, 12:30 and 16:15 and 17:30 Miami time on trading days, and when you open the app with share counts older than 60 minutes

### Reconnect Robinhood (sync failed / expired)
1. snaptrade.com → Dashboard → Connections → Robinhood → Reconnect (log in at Robinhood, read-only)
2. then 🏠 → 🔄

### Change the benchmark
1. ⚙️ מתקדם → 🎯 כוונון → מול מה משווים → choose (saved at once)

### Add a watchlist alert
1. ⚙️ מתקדם → 🎯 כוונון → 🔔 התראות משלך
2. ticker, מתי להתריע, value (price or %), דחוף?
3. הוסף התראה

### Write an instruction to Claude
1. ⚙️ מתקדם → 🎯 כוונון → 🧠 הנחיה ל-Claude
2. type it (no personal details: it is public)
3. שלח ל-Claude; the answer appears there after the next 7:20 collection (Miami time)

### Download a backup
1. 💼 → ⚙️ מתקדם → 📦 הורד את הנתונים שלי (zip)
2. weekly backups: GitHub → Releases

### Read the morning report
1. 🏠 היום → 🌎 השוק במשפט → לדוח המלא
2. or 💼 → ⚙️ מתקדם → 📰 דוח הבוקר → choose the date

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
