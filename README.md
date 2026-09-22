# execution-ads-money · Agent 10

This agent is a base. Once you have done it your way, tell your squad "update the agent to do it
like this."

The first of 3 ads agents. It connects to your own Meta ad account and turns your price into a
number: the most 1 booked call may cost you, your cap, and your daily number. It spends nothing.

## What lands on the card

`squad/ads-money-card.md`, every line with its math shown and where the number came from: your price
as the first payment, what delivering 1 client costs, the gross profit, the most to win 1 client
(gross profit divided by 6), your calls per close, the most 1 booked call may cost, the cap for the
month, the daily number, and how many booked calls the month buys at that ceiling. Meta's own
minimums are applied as floors and named when they are. Agent 12 reads this card on every build and
every read.

## Before you start

- Agent 1 has written `squad/business.md`, with your price.
- A Meta ad account.

## Install

Installed with the one line on aichrislee.com/free, then quit and reopen Claude Code.

Connect Meta Ads once, in the Claude app: **Customize, Connectors, the + button, Add custom
connector**, name it Meta Ads, URL `https://mcp.facebook.com/ads`, sign in with Facebook and pick
your business. Then quit and reopen Claude Code.

## Run it

**"Set up my ads money."** It reads every ad account your login can see and prints whether each one
is enabled and queryable, with Meta's reason word for word when it is not. It reads your price off
`squad/business.md`. Type your own numbers with the line when you have them (what delivering 1
client costs, how many calls it takes you to close 1, the month), or it works from the price alone
and says so. It shows every line of the math and writes the card.

Next: Agent 11, "Make my ads."

## What it never does

It never spends, builds or turns anything on. It never quotes someone else's cost per click or per
call. It never builds a special ad category offer (credit, jobs, housing, social issues, elections
or politics). It does not run overnight.

The full procedure is `SKILL.md`.
