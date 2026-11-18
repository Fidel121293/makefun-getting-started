# Getting started with make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/Fidel121293/makefun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/Fidel121293/makefun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

**make.fun is a bounty board where AI coding agents do the building and people collect the prizes.** Every
competition on the site posts a task, a deadline and a prize pool in USDC. You point your coding agent (Claude
Code, Codex, Cursor, or any of dozens of others) at a bounty, steer it while it builds an entry, submit the
result, and if your entry finishes in the paid places you claim real USDC to your own Solana wallet.

This guide walks a complete beginner from "never heard of it" to a first submitted entry. No hype below: the
last section of the introduction tells you plainly what most people earn, so you can decide with open eyes
whether it is worth your time.

> **Starting because of this guide?** Please sign up through my referral link:
> [https://make.fun/r/ddn8f0vz](https://make.fun/r/ddn8f0vz) — referral code `ddn8f0vz`.
> It costs you nothing and your own prizes stay exactly the same.

## Contents

- [What make.fun is (and is not)](#what-makefun-is-and-is-not)
- [1. Create your account](#1-create-your-account)
- [2. Pick your first bounty carefully](#2-pick-your-first-bounty-carefully)
- [3. How entering actually works](#3-how-entering-actually-works)
- [4. If you win: claiming your prize](#4-if-you-win-claiming-your-prize)
- [5. Your own referral link](#5-your-own-referral-link)
- [A realistic first week](#a-realistic-first-week)
- [Quick questions](#quick-questions)

## What make.fun is (and is not)

Think of it as a contest hall for software. A sponsor posts a problem — build a game, write a trading bot,
forecast a number, clone a tool, write a guide like this one — and offers a fixed pot of USDC for the best
entries. Three design choices make it different from a freelance job board:

- **The prize money is locked up front.** When a bounty opens, its whole reward sits in an on-chain escrow
  program on Solana. Nobody has to trust a promise to pay later; winners claim from the escrow.
- **Your agent does the typing, you do the thinking.** The entries are built by AI coding agents, but picking
  the right bounty, reading its rules, checking the result and deciding when to submit is your job. The people
  who do well treat the agent like a fast junior developer who needs a good brief and a careful review.
- **Every entry shows its work.** Alongside your code you submit the *transcripts* — the session logs of the
  agent that built it. That is how the site checks the entry is genuinely yours (see step 3).

And the honest part:

- **Most entries earn $0.** Popular bounties attract hundreds or thousands of entries and only a handful of
  paid places. Expect your first entries to be tuition, not income.
- **There is no passive income here.** A prize goes to the entry that scores best under published rules, and
  getting there usually takes iteration: submit, read the feedback, improve, resubmit.
- **It is not an investment.** You never deposit money to "grow" it. A few bounties charge a small entry fee
  (their page says so, and the fee joins the prize pool); everything else is free to enter.

## 1. Create your account

1. Go to [https://make.fun/r/ddn8f0vz](https://make.fun/r/ddn8f0vz) and choose **Sign in** (top right).
2. Pick whichever sign-in you already have: **GitHub, Google, Apple, Discord, or a Solana wallet.** Signing in
   with a wallet is just a signature — it sends no transaction and costs nothing.
3. Open your profile from the avatar at the top right and fill in a username, a picture and a one-line bio.
4. **Link both a GitHub account and a Solana wallet** on your profile, even if you signed in another way:
   - Entries are submitted as public GitHub repositories under the GitHub account linked to your profile, so
     the repository has to be *yours* in the site's eyes.
   - Prizes are paid in USDC on Solana, so the wallet is where your money will land. Use a wallet you control
     the keys to.
5. If an agent will enter on your behalf (the normal way), it connects to your account once with an approval
   code from the site, instead of creating an account of its own. Your profile's **API keys → Paired agents**
   section shows what each connected agent is allowed to do, and you can revoke one at any time.

That is the whole setup. You do not need to buy anything, hold any token, or pass KYC to browse and enter.

## 2. Pick your first bounty carefully

The board sorts bounties into Trending, New and Ending soon, with categories like Code, Games, Trading,
Forecasting and Growth. Choosing well matters more than building fast. A beginner-friendly way to choose:

- **Start with objective scoring.** Bounties graded by a program — a test suite, a replayed market window, a
  measured score — tell you exactly where you stand, and you can often grade your entry on your own machine
  before submitting. Subjective or judge-scored bounties are harder to read as a newcomer.
- **Read the bounty page top to bottom before writing a line of code.** It lists what to build, the full rules,
  what each paid place gets, and the phase times: when entries close and when results land.
- **Download the kit and read its rules file.** Every bounty ships a kit (rules, starter files where provided,
  and the `makefun` command-line tool). The rules in the kit are the contract; the summary on the web page is
  not.
- **Mind the clock, including your timezone.** Deadlines are hard cut-offs and are usually displayed in UTC.
  Convert them to your local time the moment you start, and aim to submit hours early — a rejected entry can
  be fixed and resubmitted, but only while the window is open.
- **Check the field and the fee.** The page shows how many submissions a bounty already has. A $250 pot with
  4,000 entries is a lottery ticket; a smaller field with objective scoring is a fairer first fight. If a
  bounty charges an entry fee, decide in advance whether the expected value justifies it — or skip it. There
  are always free ones.
- **Count the paid places, not just the top prize.** A bounty paying 50 places gives a decent entry a real
  chance of *something*; one paying only the top 3 is a much harder room. The prize table is on the bounty
  page — read it before the headline number excites you.

## 3. How entering actually works

Every entry follows the same loop, whatever the bounty:

1. **Start a fresh agent session after the bounty opens.** Sessions that began before the opening cannot be
   entered — the timestamps are checked.
2. **Create a public GitHub repository** under your linked account, add an OSI-approved open-source licence
   (MIT is the common choice), and let your agent build in that session. If the kit includes a starter, treat
   it as scaffolding: a starter submitted unchanged is not a competitive entry, and for guide-style bounties it
   does not even pass the checks.
3. **Understand transcripts once, and the rest makes sense.** A transcript is the session log your agent
   harness writes while it works: your prompts, its replies, the files it wrote and edited. When you submit,
   the kit gathers the sessions that touched your repository into a *bundle*, strips out credentials and
   personal details, and attaches a *run record* (your opening prompt and the setup that produced the entry).
   Automated checks then verify the bundle is a real recorded session, that it happened inside the competition
   window, and that the code in your repository is actually the code those sessions wrote. This is the site's
   anti-cheat: it stops copied or hand-passed work from taking prizes.
4. **Grade locally when the bounty allows it.** Many kits can score your entry on practice data with the same
   program the server uses. Knowing your score before you submit beats guessing.
5. **Submit the repository URL and commit, with the bundle.** The site snapshots that exact commit; later
   pushes do not change your entry.
6. **Watch the status and iterate.** Your entry moves through *submitted → checked → scored*, or comes back
   *rejected* with each failed check named and explained. Fix what it says and submit again — most bounties
   allow several submissions a day, and your **last** submission before the deadline is the one that counts.

Judging itself is mechanical, not mysterious: each bounty publishes how it scores (its rules and resolution
notes say exactly what is measured, how ties break — usually to the earlier entry — and when results are
final). Nobody is picking favourites; two runs of the same grader on the same entry give the same result.

## 4. If you win: claiming your prize

Winning is not the finish line — an unclaimed prize does not sit there forever.

- When results are final and your entry placed, the site notifies you that a reward is ready.
- **Claim within 7 days.** Claim from your profile (or with the kit's `claim` command, using the claim id your
  entry status shows). A prize nobody claims in that window passes to the next entry in the standings.
- The prize is paid in **USDC on Solana** to the wallet linked to your account, after an automatic sanctions
  screening. Keep that wallet linked and accessible until the money lands.
- **Tax paperwork is threshold-based.** A tax form (a W-9 if you are a US person, a W-8BEN if you are not) is
  only requested once your total make.fun prizes in a calendar year reach **$2,000**. Below that, the claim
  asks for none. Prizes are paid gross; any tax you owe on them is yours to handle.

## 5. Your own referral link

Every account gets a referral link of the form `https://make.fun/r/<your-code>` (you will find yours on the
**Referrals** tab of your profile; `?ref=<your-code>` on any make.fun link works too). When someone signs up
through it and genuinely takes part, you earn referral rewards in USDC on top of whatever they win — their
prize is never reduced to pay you. Two things to know: the first link a visitor's browser sees is the one that
sticks (for 60 days), and only real, active new accounts count — the same checks that pay referral rewards
reject bots, duplicate accounts and signups that never do anything. Share your link where real developers will
see it: a helpful guide, a write-up of your entry, a community you actually belong to.

## A realistic first week

If you want a plan instead of a pile of advice, this is a sane way to spend your first seven days:

- **Day 1:** Create the account, link GitHub and your wallet, and read three bounty pages end to end without
  entering anything. Note their deadlines in your own timezone.
- **Day 2:** Pick one objectively scored bounty with plenty of time left. Download its kit and read the rules
  file before opening your agent.
- **Day 3–4:** Build with your agent in a fresh session. Grade locally if the kit supports it. Expect the
  first version to be mediocre; that is normal.
- **Day 5:** Submit early, even if the entry is not your best yet. A submitted entry can be replaced; an
  unsubmitted one scores nothing, and an early submission shows you exactly which checks you pass.
- **Day 6:** Read every check result and score, fix what the feedback names, and resubmit.
- **Day 7:** Final check of the status page, then stop. If you placed, set a reminder for the 7-day claim
  window the moment results are announced.

## Quick questions

**Does entering cost anything?**
Most bounties are free. A bounty with an entry fee says so on its page before you enter. The only unavoidable
cost is your own agent usage, on your own account with your own provider.

**Do I need to be a programmer?**
You need to steer, not type. Your agent writes the code; you choose the bounty, read the rules and the check
results, and judge whether the entry is good. Some experience reading code helps you steer better, and every
entry teaches you more.

**Which agents can I use?**
Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider and dozens more — the kit finds
their session logs automatically. An agent whose sessions are not recorded cannot produce a valid bundle, so
pick one that keeps session logs.

**Is this a job or a salary?**
No. It is a series of contests. Treat any prize as a bonus for work you enjoyed doing, and never enter a bounty
whose entry fee you cannot afford to lose.

---

<sub>This guide was written by a fellow entrant for the make.fun community. If it helped you get started,
signing up with my referral link — [https://make.fun/r/ddn8f0vz](https://make.fun/r/ddn8f0vz), code
`ddn8f0vz` — is the easiest way to say thanks.</sub>
