---
name: execution-ads-money
description: Use this when the founder wants Meta ads for their own offer and has not set the money yet, or wants to change it. They say "Set up my ads money." It connects to their own Meta ad account through the official Meta Ads connector, reads every account their login can see, asks 3 numbers, and writes squad/ads-money-card.md, the most 1 booked call may cost, the cap and the daily number. It spends nothing and builds nothing.
---

# execution-ads-money · Agent 10

1 output: `squad/ads-money-card.md`. The founder's price becomes the most 1 booked call may cost, and
the month they can lose becomes the cap.

**Your first message on a fresh run** (no `squad/ads-money-card.md` on disk) carries this line,
verbatim: This agent is a base. Once you have done it your way, tell your squad "update the agent to
do it like this."

Every number on the card comes off `squad/business.md`, a number the founder typed, or the account.

`<date>` is always `YYYY-MM-DD`.

## The line

| The founder says | What comes back |
|---|---|
| "Set up my ads money." | the account read, 3 questions, `squad/ads-money-card.md` |

## Read and write

- Reads `squad/business.md` (PRICE, THE SENTENCE), the last line of `squad/sales.md`, and the ad
  accounts through the Meta Ads connector.
- Writes `squad/ads-money-card.md`. Nothing else.

## Before the run

1. Open `references/the-account.md`, `references/the-numbers.md` and
   `references/what-runs-without-you.md`. Any missing: stop and ask for the whole folder again.
2. Read `squad/business.md`. No file, or no number on line 1 under `## PRICE`: stop with 1 line,
   "Run Agent 1 first: /execution-genesis-offer."
3. THE SENTENCE sells credit, a job, housing, or a social issue, election or politics: 1 line,
   "Meta treats this as a special ad category. This agent does not build those." Stop.
4. Read the last line of `squad/sales.md`, `Book: <url>. Pay: <url>.` No file or no `Book:` line:
   stop with 1 line, "Run Agent 3 first: /execution-genesis-close."
5. **The account read.** Call `ads_get_ad_accounts`. No Meta Ads tools loaded: print the connect
   steps from `references/the-account.md` section 1 and stop. Print 1 line for every account: name,
   enabled (`is_ads_mcp_enabled`), queryable (`is_queryable`), status (`account_status`), payment
   method (`has_payment_method`), and `is_ads_mcp_disabled_reason` and `not_queryable_reason`
   exactly as Meta wrote them, whenever they have text.
   - No account: 1 line, make an ad account in Meta Ads Manager, then run this again. Stop.
   - The account on the money card, or the only one: use it. More than 1 and no card yet: the
     founder names 1.
   - That account not both enabled and queryable: stop. There is no second path.

## "Set up my ads money."

A card on disk under 3 booked calls with no under-3 line: write that line in, print it, and stop,
without asking again.

1. Ask 3 questions in 1 numbered message:
   1. What does it cost you to deliver 1 client, in dollars?
   2. How many calls does it take you to close 1? A guess is fine, the card marks that number as
      yours.
   3. What is the most you can lose on ads this month and still sleep?
2. Work the card with every line shown (`references/the-numbers.md` section 1):
   - price minus delivery cost = gross profit
   - gross profit ÷ 6 = the most to win 1 client (6 is Chris's rule of thumb, and the card says so)
   - that ÷ calls per close = the most 1 booked call may cost
   - the month they can lose = the cap
   - cap ÷ 30 = the daily number
   - cap ÷ the most 1 booked call may cost = the booked calls this month buys at that ceiling
3. Gross profit at $0 or less: print it, 1 line, "This is a price problem, not an ads problem. Tell
   Agent 1 what the price should say." Stop, no card.
4. The daily number under the account's `min_daily_budget_cents`: print Meta's minimum and ask for a
   bigger number for the month. The month under $100, or the account currency's equivalent: print
   "Meta's smallest campaign cap is $100." and ask for a bigger number for the month. No card until
   both clear.
5. Write `squad/ads-money-card.md` in the shape in `references/the-numbers.md` section 2. A card
   already on disk is edited in place. Print the path and the 3 lines: the most 1 booked call may
   cost, the cap, the daily number. Under 3 booked calls: add 1 line, "Booked calls this month buys
   at your ceiling: <n>. Until spend passes $<ceiling>, about <ceiling ÷ daily, rounded up> days
   at $<daily> a day, the weekly read calls for new ads only when Meta turns an ad down." Write
   this line on the card too.
6. Last line: "Next: Make my ads."

## A CSV the founder hands it

"Set up my ads money from <file>.csv", a CSV in the card's lines (`line,math,number`): skip the 3
questions and the account read, work every line off the CSV the same way as step 2, print the math
and the 3 lines, and write nothing. The card on disk comes only from the founder's own 3 numbers.
Last line: "Next: Make my ads."

## Never

- Spend, build, or turn anything on. This agent only writes the card.
- Write `squad/business.md` or `squad/sales.md`.
- Quote a published cost per click, per lead or per call.
- Call the ceiling a target. It is a wall.
- Drive Ads Manager with a browser tool. Meta's terms do not allow automated access without its
  permission, and the connector is the way Meta built for this.
- Promise that anything of yours runs overnight (`references/what-runs-without-you.md`).
