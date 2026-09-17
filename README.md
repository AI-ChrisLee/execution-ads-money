# execution-ads-money · Agent 10

This agent is a base. Once you have done it your way, tell your squad "update the agent to do it
like this."

The first of 3 ads agents. It connects to your own Meta ad account and turns your price into a
number: the most 1 booked call may cost you, your cap, and your daily number. It spends nothing.

## Before you start

- Agent 1 has written `squad/business.md`, with your price.
- Agent 3 has written `squad/sales.md`, with your booking link on its last line.
- A Meta ad account.

## Install

Installed with the one line on aichrislee.com/free, then quit and reopen Claude Code.

Connect Meta Ads once, in the Claude app: **Customize, Connectors, the + button, Add custom
connector**, name it Meta Ads, URL `https://mcp.facebook.com/ads`, sign in with Facebook and pick
your business. Then quit and reopen Claude Code.

## Run it

**"Set up my ads money."** It reads every ad account your login can see and prints whether each one
is enabled and queryable, with Meta's reason word for word when it is not. It asks 3 numbers: what
delivering 1 client costs, how many calls it takes you to close 1, and the most you can lose on ads
this month ($100 at least). It shows every line of the math and writes `squad/ads-money-card.md`:
the most 1 booked call may cost, the cap, the daily number.

Next: Agent 11, "Make my ads."

## What it never does

It never spends, builds or turns anything on. It never quotes someone else's cost per click or per
call. It never builds a special ad category offer (credit, jobs, housing, social issues, elections
or politics). It does not run overnight.

The full procedure is `SKILL.md`.
