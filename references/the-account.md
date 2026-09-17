# The account: Meta Ads

Every call this agent makes, with the fields it reads back. Read the live tool list every run. When
a name here and the live list disagree, the live list wins and the founder hears 1 line about it.

## 1. Connect Meta Ads, once

The official Meta Ads connector is a custom connector, added in the Claude app:

> Claude, Customize, Connectors, the + button, Add custom connector. Name it Meta Ads, URL
> `https://mcp.facebook.com/ads`. Sign in with Facebook and pick the business that owns the ad
> account.

Then quit Claude Code and open it again in the same folder. Claude Code signed in with the same
Claude account picks up the connector. No developer app, no key to paste.

## 2. The account read

`ads_get_ad_accounts` returns, per account:

| Field | Printed as | Stops the run when |
|---|---|---|
| `is_ads_mcp_enabled` | enabled | false |
| `is_ads_mcp_disabled_reason` | the reason, exactly as written | (printed whenever it has text) |
| `is_queryable` | queryable | false |
| `not_queryable_reason` | the reason, exactly as written | (printed whenever it has text) |
| `account_status` | status | (printed) |
| `has_payment_method` | payment method | never here; the launch card says to add one before go |
| `currency` | the card's currency | |
| `min_daily_budget_cents` | Meta's minimum a day | the daily number is under it (the card asks for a bigger number for the month) |

**The smallest cap.** Meta's Marketing API campaign reference (read 2026-09-16) gives `spend_cap` "a
minimum value of $100 USD (or approximate local equivalent)". A month under that gets no card: print
"Meta's smallest campaign cap is $100." and ask for a bigger number for the month.

An account that is not both enabled and queryable is never used. No call here changes either flag.
Print the reasons as Meta wrote them and add nothing about why it happened.

Page more than 50 accounts with `cursor`. Send the same `client_conversation_id` on every Meta
call in a run.

## 3. What the connector does not have

No rules tool, no lead form tool, no tool that reads the calendar. Nothing here drives Ads Manager
in a browser, since Meta's terms do not allow automated access without its permission. The
connector is the way Meta built for this.
