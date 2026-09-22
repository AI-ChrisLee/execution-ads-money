# The numbers and the card

Every number here comes off the founder's price, a number the founder typed with the line, or the ad
account. Nothing here is a benchmark somebody published.

## 1. The money card

| Line | Working | Where it comes from |
|---|---|---|
| Price | the first payment a client makes | line 1 under `## PRICE` in `squad/business.md` |
| Delivery | what delivering 1 client costs | typed with the line, else $0, marked `not typed` |
| Gross profit | price minus delivery | arithmetic |
| Most to win 1 client | gross profit ÷ 6 | 6 is Chris's rule of thumb, never a measured number |
| Calls per close | out of how many calls they close 1 | typed with the line, else 1, marked `not typed` |
| Most 1 booked call may cost | most to win 1 client ÷ calls per close | arithmetic |
| The cap | the month | typed with the line, else the most to win 1 client, marked `not typed`; $100 at least (Meta's smallest campaign cap) |
| Daily number | cap ÷ 30 | arithmetic, Meta's `min_daily_budget_cents` at least |
| Calls this month buys | cap ÷ most 1 booked call may cost, rounded down | arithmetic |

**The first payment.** A one-time price is the price. "A month" is 1 month's fee. "Setup + $N a
month" is the setup plus the first month. The card says which.

**Why 6.** It is Chris's rule of thumb for a business where people do the work, and the card says
it is his rule of thumb.

**A worked line, numbers only.** Price $3,000, delivery $600: gross profit $2,400. ÷ 6 = $400 to
win 1 client. Closes 1 in 4 calls: $100 is the most 1 booked call may cost. The month is $900: the
cap is $900, the daily number $30, and the month buys 9 booked calls at that ceiling.

Round every dollar figure down to the cent.

Under the ceiling, the founder keeps going. Over it, the weekly read calls for new ads.

## 2. The card file

`squad/ads-money-card.md`, 1 page, edited in place:

```
# Ads money card · <YYYY-MM-DD>

Account: <ad account name> · <ad account id> · <currency>

## THE CEILING
Price, the first payment: $<n> (squad/business.md, PRICE: <the price | 1 month's fee | the setup + the first month>)
Delivery per client: $<n> (<typed | not typed, $0>)
Gross profit: $<price> - $<delivery> = $<n>
Most to win 1 client: $<gross profit> ÷ 6 = $<n> (6 is Chris's rule of thumb, not a measured number)
Calls per close: <n> (<typed | not typed, 1>)
Most 1 booked call may cost: $<n> ÷ <calls> = $<n>

## THE CAP
The month: $<n> (<typed | not typed, the most to win 1 client | Meta's smallest cap>). This is the cap, the most this campaign can spend.
Daily number: $<cap> ÷ 30 = $<n> (<or Meta's minimum a day>)
Booked calls this month buys at your ceiling: <n>
```

Agent 12 reads this card for the account, the daily number, the cap and the ceiling, on every build
and every read. A new month is typed with "Set up my ads money." and the card is edited in place.

## 3. Banned, in any run

| Claim | Why |
|---|---|
| A published cost per click, per lead or per call | nobody publishes an honest one for a solo founder's offer; the ceiling comes off their own price |
| Any account being disabled, tied to Claude | nothing shows a cause; print Meta's reason as written |
