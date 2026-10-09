# Kamai: what a delivery rider really keeps per hour

*Product case study · Nandini Kshatriya · October 2026*

> **How to read the labels.**
> - <span class="tag v">Verified</span> a figure I read in the published source, with its date, sample and method.
> - <span class="tag c">Company claim</span> a figure published by a platform about itself.
> - <span class="tag q">Qualitative</span> a quote, reported complaint or single case.
> - <span class="tag a">Assumption</span> my judgment, untested.
> - <span class="tag s">Simulated</span> the example rider "Ravi" and all his numbers.
>
> I have not interviewed riders. Every user insight here comes from published surveys, studies, government documents and reporting, listed at the end.

## In short

- **Problem:** a food or quick-commerce rider sees gross pay per order. They don't see what they keep per hour after fuel, the bike, the phone and unpaid waiting. Pay rules and incentive targets change often, and the platforms, unions and researchers each publish a different "earnings per hour".
- **What I built:** a phone-first, bilingual (English/Hindi) app where a rider logs a shift in about six fields. Kamai turns it into:
  - **real earnings per logged-in hour**
  - **a pay-cut alert per app**
  - **a verdict on whether an incentive target is worth the extra hours**
  - **a 14-day cash plan** that lines weekly payouts up against daily fuel and monthly EMIs
  - **a monthly statement** the rider owns
- **Key product decision:** count *logged-in* hours, waiting included, and include EMI and phone costs. Published "net" figures usually leave those out. <span class="tag s">Simulated</span> Over 28 days the example rider grosses ₹102 per logged-in hour, the figure Zomato reports. Fuel and repairs take 27%, close to IDInsight's ~32%. Adding EMI and phone takes costs to 43% and leaves ₹58 an hour. These figures shift slightly with the date, because the example is generated relative to today.
- **Not claimed:** no users, no usage numbers, no outcomes. The example rider is simulated.

## 1. Problem

India's delivery riders are paid per order, plus distance, incentives and surge. They pay their own fuel, repairs, phone and often a vehicle EMI or daily scooter rent. Three facts make "how much did I really earn?" hard to answer:

1. **Everyone measures it differently.**
   - Zomato reported partners earn **₹102 per logged-in hour** (2025, gross, excluding tips) and assumed about 20% for fuel and maintenance <span class="tag c">Company claim</span>.
   - A phone survey of 2,547 platform workers, sampled from a platform's admin data, measured operating costs at **about 32% of gross** <span class="tag v">Verified</span> (IDInsight, Mar 2025).
   - A union put net pay at **about ₹81 an hour** <span class="tag q">Qualitative</span> (TGPWA, Jan 2026, with no cost inputs disclosed).
2. **Waiting is unpaid but real.** In a survey of 5,082 delivery workers across 8 cities, 42.8% reported about 1 hour a day of idle time and 34.1% about 2 hours <span class="tag v">Verified</span> (PAIGAM–IFAT, *Prisoners on Wheels?*, ~Mar 2024, purposive and snowball sampling, union-linked). The Economic Survey 2025-26 recommends minimum pay that *includes waiting time* <span class="tag v">Verified</span> (via PTI, 29 Jan 2026).
3. **Pay rules change without warning.** Reported examples:
   - Swiggy widened the delivery radius while base pay stayed at ₹20 (Mumbai, Oct 2023).
   - Blinkit moved Saturday payouts to weekday rates (May 2024).
   - Workers alleged Zepto cut per-order pay from ₹30 to ₹10–15 (Hyderabad, May 2025), which Zepto disputed.

   On 31 Dec 2025, striking workers demanded a review of "algorithms that set incentives and payouts" <span class="tag q">Qualitative</span>.

**Job to be done:** "Before I log in, or decide to chase a target, I want to know what an hour of riding actually leaves in my pocket, so I can choose when, where and for which app to work, and spot a pay cut before it costs me a week."

## 2. Research (secondary only)

### 2a. Earnings and costs

| Finding | Source · date | Sample · method | Label |
|---|---|---|---|
| ₹102 per logged-in hour (2025), up from ₹92, plus ₹2.6/hr in tips | Zomato CEO post, via Business Today, 2 Jan 2026 | All Zomato partners, company data | <span class="tag c">Company claim</span> |
| Operating costs ≈ 32% of gross and net ₹75–115/hr. The two write-ups of the same survey disagree, so I quote the range. | IDInsight, Mar 2025, and IDR, 20 Jan 2026 | 2,547 workers, phone survey from platform admin frame | <span class="tag v">Verified</span> |
| 57.75% spend ₹201–400 a day on fuel and 50.7% ride 101–150 km a day | PAIGAM–IFAT, ~Mar 2024 | 5,082 delivery workers, 8 cities, face-to-face survey | <span class="tag v">Verified</span> |
| 34.4% net under ₹10,000 a month after expenses (Lucknow 69.65%, Bengaluru 8.42%) | Same | Same | <span class="tag v">Verified</span> |
| One rider's month: ₹14,000 gross. Costs: fuel ₹5,100, phone EMI ₹1,200, maintenance ₹800, data ₹600, plus fines and punctures. About ₹6,080 kept. | *The India Forum*, 28 Jul 2025 | 1 worker, participant observation | <span class="tag q">Qualitative</span> |
| Only 2 of 11 platforms could show workers earn the local minimum wage after costs | Fairwork India ratings, as reported by BusinessWorld in 2024 | Desk research, interviews, platform documents | <span class="tag v">Verified</span> (secondary report) |

### 2b. Hours, incentives and money stress

| Finding | Source · date | Sample · method | Label |
|---|---|---|---|
| 55.1% work 10–12 hours a day and 48.24% have no weekly day off | PAIGAM–IFAT, 2024 | 5,082 | <span class="tag v">Verified</span> |
| The average Zomato partner worked 38 days in 2025, at about 7 hours a day. 2.3% worked more than 250 days | Zomato CEO post, Jan 2026 | Company data | <span class="tag c">Company claim</span> |
| About 77% of workers are less than full-time | IDInsight, 2025 | 2,547 | <span class="tag v">Verified</span> |
| 47.75% get no minimum guarantee or incentive, 32.56% do and 19.69% sometimes do | PAIGAM–IFAT, 2024 | 5,082 | <span class="tag v">Verified</span> |
| "If we lose a streak… then we lose incentives" | Al Jazeera, 28 Jan 2026 | 1 rider quoted | <span class="tag q">Qualitative</span> |
| Waiting is ~25–30% of active time and "generally not factored into compensation". Penalties are opaque. | IIIT-Hyderabad, arXiv 2504.17697, 2025 | 14 interviews | <span class="tag q">Qualitative</span> |
| Half of asset owners borrowed to buy the asset, and about a third of those missed a repayment | IDR (IDInsight), Jan 2026 | 2,547 | <span class="tag v">Verified</span> |
| About 60% find it hard to meet monthly expenses. About 87% report being affected by ID blocking | PAIGAM–IFAT, 2024 | 5,082 | <span class="tag v">Verified</span> |
| Default payout is weekly. Swiggy launched an "Early Cashout" in Sep 2026 | Restaurant India, 18 Sep 2026 | Company announcement | <span class="tag c">Company claim</span> |

### 2c. Policy context

- **Code on Social Security:** came into force on 21 Nov 2025 <span class="tag v">Verified</span> (PIB). The 2026 central rules reportedly count eligibility as 90 days with one aggregator, or 120 across several. That comes from a law-firm summary, not the gazette, so the app shows it "as reported".
- **Karnataka:** notified a welfare fee of 1%, with a ₹0.50 cap for two-wheeler delivery (I have not yet confirmed from the gazette whether the cap is per trip), from Feb 2026. The Act also requires disclosure of automated decision systems.
- **Telangana:** the 2025 draft Bill gives workers a right to information about deductions and the systems that set earnings.
- **e-Shram:** more than 5 lakh gig workers were registered by Dec 2025 (Lok Sabha reply).

### 2d. Two segments, not one

Union surveys sample committed full-timers: 55% work 10–12-hour days. Company and admin-sampled data covers the whole roster, which is mostly casual (Zomato's average partner worked 38 days a year). Both are true, for different people. <span class="tag a">Assumption</span>: Kamai's first users are full-timers, because the money at stake is larger for them and they already think in weekly targets and EMIs.

### 2e. What the evidence does *not* answer

- What share of earnings comes from incentives, and how often targets change.
- The burden of carrying cash-on-delivery money.
- Independent weekly costs of renting an e-scooter.
- **Whether riders will log shifts by hand.** This is the riskiest assumption for Kamai, and nothing published answers it.

## 3. Users

- **Primary: the full-time rider.** Rides 9–12 hours, usually for one main app and sometimes a second. Owns a petrol bike, half the time on a loan, and pays a phone EMI. Gets paid weekly, pays fuel daily, and owes EMIs monthly. <span class="tag a">Assumption</span>, built from the surveys above.
- **Secondary: the part-time rider,** who needs only "was today worth it?"
- **Not for (yet):** cab drivers, whose costs and commissions work differently, and riders on platform-owned vehicles.

## 4. Competitors and alternatives

| Alternative | What it does | Gap for my rider |
|---|---|---|
| Platform partner apps (Swiggy, Zomato, Zepto…) | Daily earnings, orders, incentive progress | One platform at a time and gross only. No costs, no net per hour. The platform has little reason to show net figures. |
| Gridwise, Stride (US) | Syncs gig earnings, tracks mileage and expenses for US tax | Not available in India and built around US mileage deductions |
| KarmaLife and similar fintechs | Earned-wage access and credit for gig workers, sold through employers | Credit, not earnings intelligence. B2B distribution. |
| EV rental apps (Bounce Daily, Yulu, Zypp) | Rent and battery swaps. Bounce Daily "from ₹250/day" | Show what you pay them, not what you keep |
| A notebook or WhatsApp notes | Free, flexible, already used | No per-hour view, no trend, no alert |

I found no Indian product that combines earnings across apps with real costs and net per logged-in hour.

## 5. User journey (as built)

1. **First open.** The example rider shows the value before any typing. "Start my own log" opens vehicle and cost settings with sensible defaults.
2. **After each shift (about 30 seconds).** Enter date, app, slot, hours, orders, km and order pay from the platform's earnings screen. Incentive, tips, waiting and actual fuel are optional.
3. **Today.**
   - Real earnings per hour for the last day, the week or 28 days.
   - The gap against the gross figure the app shows.
   - Where the money went: fuel, fixed costs, and waiting share.
   - Alerts.
4. **Week.**
   - Profit and loss.
   - Which app pays better per hour after fuel.
   - Best time slots.
5. **Targets.** Enter an incentive and get a verdict: worth chasing / only a little better than usual / not worth extra hours / not reachable safely in the time left. Every input behind the verdict is shown.
6. **Cash plan.** A 14-day projection of cash with payouts, fuel, home spending and bills, the lowest point, and how many hours would cover a shortfall.
7. **Hisab.**
   - A monthly statement to copy as text or CSV.
   - Days worked per app this financial year, against the reported 90/120-day thresholds.
   - Backup and restore.

## 6. PRD (MVP)

| ID | User story | Acceptance criteria |
|---|---|---|
| K1 | As a rider, I can log a shift fast | Required fields: date, app, slot, hours, orders, km, order pay. The app remembers the last app used. Errors say what to fix (for example, waiting cannot exceed hours logged in). Future dates are rejected. |
| K2 | As a rider, I see what I keep per hour | Net = earned − fuel (entered, or km ÷ mileage × price) − fixed costs (EMI + phone + repairs per riding day, plus daily rent), spread by hours. Divided by logged-in hours. Gross per hour shown alongside. |
| K3 | As a rider, I'm warned when an app cuts pay | Per app: last 7 days vs the 28 before. Needs ≥15 and ≥30 orders. Fires at a ≥10% drop per order. Per-km change is shown as well. |
| K4 | As a rider, I know if a target is worth it | Uses my own orders per hour, km per order and pay per order on that app. Pay per order comes from the last 7 days when there are ≥15 orders, so a fresh cut isn't averaged away. "Worth" means at least 1.2× my usual ₹/hr after fuel. "Not reachable safely" when usual hours plus extra per day exceed 13. |
| K5 | As a rider, I can see if money will run short | 14-day projection. Weekly payout for the previous Monday–Sunday week. Running weeks estimated from the 28-day average. Bills on their day of the month. Shows the lowest point, "safe to spend" after the buffer, and hours needed to cover a gap. |
| K6 | As a rider, I own a record of my work | Monthly statement per app, copied as text or CSV, labelled "self-recorded, not verified by platforms". Days worked per app this financial year. |
| K7 | As a rider, my data stays mine | Stored on the phone only. Backup is a text string to keep in WhatsApp or notes. No account, no server. |
| K8 | As a Hindi-first rider, I can use it in Hindi | Every rider-facing string in Hindi. Indian number formatting (₹1,23,456). |

**Non-goals:** reading platform data (no APIs exist, and SMS or screenshot parsing raises privacy and reliability issues), lending, multi-device sync, and cab drivers.

## 7. MVP scope and what I cut

| Decision | Why |
|---|---|
| **In:** logged-in hours as the denominator | That is how Zomato reports its ₹102, and how the Economic Survey wants pay floors set. Waiting must show up as a cost to the rider. |
| **In:** EMI and phone in fixed costs | Riders pay them and published cost shares usually leave them out. Showing both numbers makes the difference visible. |
| **In:** recent pay rate in the target verdict | In testing, the 28-day average hid the simulated Zepto cut and rated a target "a little better than usual" when it was worse. Kamai now uses the last 7 days' rate. |
| **In:** no chart library | Low-end phones and patchy data. Charts are hand-drawn SVG and the app is one small page that works offline. |
| **Out:** automatic import from platform apps | No APIs exist, and SMS or screenshot parsing is a v2 bet with real privacy risk |
| **Out:** loans or advances | A cash-short rider is a vulnerable user. Kamai shows the gap and the hours that would close it, and does not sell credit. |
| **Out:** EV-vs-petrol calculator | Evidence is weak (EV riders reportedly earn 20% more, correlational). Settings already support EV rent and per-km charging. |

## 7b. Design decisions in the October redesign

The first version worked but looked like a dashboard. Riders check it at a signal or a restaurant counter, often one-handed on a budget Android phone, so I rebuilt the interface around three rules.

| I chose | Over | What it costs |
|---|---|---|
| One big number first (kept per hour), with the gross figure as a sentence under it | A row of equal KPI cards | Less on screen at once. The rider gets the answer in one glance, and the gap between "app says" and "you keep" is the point of the product. |
| The cash verdict above the cash chart | Chart first | The chart becomes supporting detail. Most riders want "will I run short, and when", not a line graph. |
| A bottom tab bar and a floating "Log a shift" button on phones | Top tabs everywhere | Takes vertical space. Logging is the action that keeps every number honest, so it is always one tap away. |
| Hand-drawn SVG charts and self-hosted fonts | A chart library and Google Fonts | More code to maintain. The page stays small and works offline as an installable web app. |
| A warm ledger palette where green only ever means money kept | A multi-colour dashboard | Fewer colours to work with. Fuel, fixed costs and kept money stay readable in both light and dark mode. |
| English and Hindi with Devanagari-ready fonts (Baloo 2 and Mukta) | English only | Every new string needs two translations. A large share of riders in North India read Hindi first. |

On wide screens the app sits in a phone-width column, and a side panel explains how each number is calculated for anyone reviewing the project. On phones that explanation folds into a "How is this calculated?" section at the bottom of each tab.

## 8. Prioritization (RICE, with evidence strength)

Reach is the share of an assumed 1,000-rider pilot affected. Impact (0.5–3), confidence and effort are my estimates <span class="tag a">Assumption</span>. Confidence follows the strength of the research behind each feature.

| Feature | Evidence | Reach | Impact | Confidence | Effort (weeks) | RICE | Decision |
|---|---|---|---|---|---|---|---|
| Net per logged-in hour | Strong: three conflicting published figures, cost surveys | 1,000 | 3 | 80% | 1 | 2,400 | MVP |
| Fast shift log | Needed for everything, but manual logging is unvalidated | 1,000 | 2 | 50% | 1 | 1,000 | MVP |
| Pay-cut alert | Medium: repeated reported cuts | 700 | 2 | 60% | 0.5 | 1,680 | MVP |
| Target evaluator | Medium: opacity well documented, size unknown | 500 | 2 | 50% | 1 | 500 | MVP |
| 14-day cash plan | Medium: borrowing and missed repayments | 600 | 2 | 50% | 1.5 | 400 | MVP |
| Monthly statement + days worked | Medium: blocking, new grievance rights | 600 | 1 | 60% | 0.5 | 720 | MVP |
| Hindi UI | Strong for reach in North India. Kannada and Telugu next. | 1,000 | 1 | 80% | 0.5 | 1,600 | MVP |
| SMS / screenshot import | Would cut logging effort, with privacy risk | 1,000 | 2 | 30% | 4 | 150 | v2 |
| Welfare enrolment nudges (e-Shram, PM-JAY) | Weak as a core job | 400 | 1 | 40% | 1 | 160 | v2 |

## 9. Success metrics

- **North Star:** riders who log at least 5 shifts in a week and open Today or Targets on 3 or more days that week. They are using the number to plan, not only recording.
- **Inputs:**
  - Median time to log a shift (target under 30 seconds) <span class="tag a">Assumption</span>.
  - Week-4 logging retention.
  - Share of riders who set their own costs instead of keeping the defaults.
- **Decision proxies:**
  - Share of target verdicts followed by a matching change in hours that week.
  - Share of pay-cut alerts followed by a change in that app's share of hours within 2 weeks.
- **Rider outcome (long-term, self-reported):** change in net per logged-in hour after 8 weeks, compared with riders not yet onboarded.
- **Guardrails:**
  - Average logged-in hours per day must not rise. Kamai should not push riders into longer, less safe days.
  - The share of riders who stop logging after a "not worth it" verdict.

## 10. Experiment plan

None of these has been run.

1. **Net first or gross first?**
   - *Setup:* randomise new users to a Today screen that leads with net per hour (current) or gross per hour with net below it.
   - *Primary metric:* week-4 logging retention.
   - *Guardrail:* hours logged per day.
   - *Hypothesis:* leading with net builds more trust, and so more retention, than the familiar gross number, even though the net number is lower.
2. **Logging friction.**
   - *Setup:* the current 7 required fields against 4 (hours, orders, pay, km).
   - *Metrics:* completion rate, time to log, and accuracy of net per hour against riders who enter actual fuel.
3. **Target evaluator effect.**
   - *Setup:* at rollout, show verdicts to half of riders with an active target.
   - *Primary metric:* net per logged-in hour over the target week.
   - *Guardrail:* total hours.
   - *Sizing:* with roughly 200 riders per arm and a standard deviation near ₹15/hr <span class="tag a">Assumption</span>, a difference of about ₹4.2/hr is detectable at 80% power (two-sided, α = 0.05).

## 11. Launch strategy

- **Distribution through riders' own networks:**
  - Rider WhatsApp groups, hub and dark-store waiting areas.
  - Worker associations, which have already surveyed 5,000+ riders.
  - EV rental hubs, where riders already handle money and paperwork.
- **Language:** Hindi first, then Kannada and Telugu for Bengaluru and Hyderabad, where worker laws are moving.
- **Pilot gate:**
  - ≥40% of onboarded riders still logging in week 4 <span class="tag a">Assumption</span>.
  - Median log time under 30 seconds.
  - No rise in hours per day.
- **Business model options:**
  - (a) Free to riders, funded by grants or worker organisations. The cleanest fit with trust.
  - (b) B2B2C with EV rental operators, who want riders to stay solvent.
  - (c) Later, regulated referrals for insurance or savings.

  Selling rider data to platforms or lenders is ruled out, because it would break the product's promise.

## 12. Risks and ethics

- **Precision theatre.** Fuel is estimated from km unless the rider enters what they paid. The log form says so and asks for actual spend when the rider has it.
- **Safety.** The target evaluator flags days over 13 hours as not reachable safely instead of optimising them.
- **Record misuse.** The statement says it is self-recorded and unverified, so nobody mistakes it for a platform document.
- **Privacy.** No server and no account. Backup is in the rider's hands.

## 13. What I got wrong along the way

- **The incentive check.** My first version priced the remaining orders at the 28-day average pay. In the simulated Zepto cut, that called a target "a little better than usual" when, at this week's rate, it paid less than an ordinary hour. The evaluator now uses the recent rate and labels it.
- **The first example rider** earned about ₹84 an hour gross, well below Zomato's reported ₹102. I recalibrated the simulation to ₹102 so the example sits on the published figure rather than making the problem look worse than the evidence supports.

## 14. Connection to ReviewRadar

My other project, ReviewRadar, mines app-store reviews. I looked for a public dataset of delivery-*partner* app reviews to test rider pain points from that side too, and found none. Its "rider apps" scenario is therefore simulated. The natural next step is to scrape partner-app reviews with the open-source scraper and run them through ReviewRadar's taxonomy (payout delays, incentive rules, ID blocks).

## 15. Limits and next steps

**Limits.**
- No rider has used Kamai. Every screen is tested against a simulated rider, not real logs.
- The riskiest assumption is still unanswered: will riders log shifts by hand, every day, for weeks?
- Costs are only as good as what the rider enters. Fuel defaults to a km-based estimate.
- The 90 and 120 day social-security thresholds come from a law-firm summary, not the gazette.

**Next steps.**
1. Put the installable app in front of 5 to 10 riders through a worker association or an EV rental hub, with consent, and measure one thing: how many still log a shift on day 7.
2. Time the shift form with real riders and cut it to four required fields if the median is above 30 seconds.
3. Scrape delivery-partner app reviews and run them through ReviewRadar to test whether pay cuts and incentive rules dominate rider complaints the way the surveys suggest.

## Sources

- PAIGAM & IFAT, *Prisoners on Wheels?* (~Mar 2024): https://tgpwu.org/wp-content/uploads/2024/03/Report-Final-Print-1.pdf
- IDInsight, "The changing landscape of work", 24 Mar 2025: https://www.idinsight.org/article/the-changing-landscape-of-work-insights-into-indias-delivery-platform-gig-workforce/
- IDR, "What the data reveals about India's gig workers", 20 Jan 2026: https://idronline.org/article/livelihoods/what-the-data-reveals-about-indias-gig-workers/
- Business Today, Zomato partner earnings, 2 Jan 2026: https://www.businesstoday.in/amp/latest/corporate/story/look-at-the-full-picture-deepinder-goyal-breaks-down-delivery-partner-earnings-with-hard-facts-509252-2026-01-02
- IANS, TGPWA response, 3 Jan 2026: https://ianslive.in/not-decent-work-gig-workers-union-slams-zomato-ceos-claims--20260103134856
- NCAER, food delivery platform workers report, 28 Aug 2023 (N = 924, Prosus-funded): https://www.ncaer.org/wp-content/uploads/2023/08/NCAER_Report_Platform_Workers_August_28_2023.pdf
- *The India Forum*, "Twenty Rupees, Twenty Minutes", 28 Jul 2025: https://www.theindiaforum.in/tiffin/twenty-rupees-twenty-minutes-what-i-learned-working-indias-gig-economy
- Suvarnapathaki et al. (IIIT-Hyderabad), arXiv 2504.17697, 2025: https://arxiv.org/pdf/2504.17697
- Al Jazeera, 28 Jan 2026: https://www.aljazeera.com/features/2026/1/28/india-curbs-grocery-under-10-minutes-but-riders-must-still-fatally-race
- BusinessWorld on the Fairwork India ratings (2024 article, report year not stated): https://businessworld.in/article/fairwork-india-report-exposes-unfair-working-conditions-for-gig-workers-535781
- Outlook Business, Swiggy Mumbai strike, 10 Oct 2023: https://www.outlookbusiness.com/news/swiggy-workers-strike-over-change-in-payouts-enters-third-day
- Outlook Business, Blinkit strike, 21 May 2024: https://www.outlookbusiness.com/corporate/blinkit-delivery-partners-strike-over-pay-cuts-in-delhi-and-mumbai-report
- MediaNama, Zepto Telangana, 23 May 2025: https://www.medianama.com/2025/05/223-zepto-workers-backlash-telangana/
- Outlook Business, strike demands, 31 Dec 2025: https://www.outlookbusiness.com/corporate/no-more-10-minute-orders-union-demands-to-scrap-quick-delivery-model-amid-gig-workers-strike
- The Week / PTI, Economic Survey 2025-26, 29 Jan 2026: https://www.theweek.in/wire-updates/business/2026/01/29/40-pc-gig-workers-earn-below-rs-15k-month-economic-survey-advocates-minimum-per-task-earnings.html
- PIB, labour codes in force, 21 Nov 2025: https://labour.gov.in/sites/default/files/pib2192463.pdf
- Bhatt & Joshi Associates, 2026 rules summary (secondary): https://bhattandjoshiassociates.com/indias-gig-economy-workers-under-social-security-code-2020-legal-rights-implementation-and-2026-rules-update/
- SCC Online, Karnataka welfare fee, 18 Feb 2026: https://www.scconline.com/blog/post/2026/02/18/karnataka-government-notifies-gig-workers-welfare-fee-mandatory/
- PRS India, Telangana draft Bill 2025: https://prsindia.org/bills/states/the-draft-telangana-gig-and-platform-workers-registration-social-security-and-welfare-bill-2025
- NewsOnAir, e-Shram registrations, 1 Dec 2025: https://www.newsonair.gov.in/government-says-31-crore-unorganised-and-5-lakh-gig-workers-now-on-e-shram-portal
- Restaurant India, Swiggy Early Cashout, 18 Sep 2026: https://www.restaurantindia.in/news/swiggy-introduces-early-cashout-for-food-delivery-partners-ending-weekly-payout-wait.n17262
- Gridwise expense tracker: https://gridwise.io/features/expense-tracker
- IBS Intelligence, LoadShare and KarmaLife, 10 Aug 2022: https://ibsintelligence.com/ibsi-news/loadshare-partners-with-karmalife-to-launch-a-credit-program/

Full research notes, with every figure's sample size, method and verification status, are in `research/kamai_secondary_research.md`.
