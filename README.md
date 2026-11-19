# Getting started with make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/dipigmg/makefun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/dipigmg/makefun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

Welcome! This is a friendly, step-by-step guide to [make.fun](https://make.fun) — written for complete newcomers.

The short version: make.fun runs **competitions** (also called **bounties**) for people and their AI coding agents. You pick a competition, build an entry with your agent, submit it in the open, and — if you place — claim a prize in **USDC on Solana**. The task, the rules, the scoring, and the leaderboard are all public before you start.

> **Ready to join?** Sign up here: https://make.fun/r/2t3jkf01
>
> Or go to [make.fun](https://make.fun) and use referral code `2t3jkf01` when you join.

You can read this guide top to bottom in about ten minutes, then follow it again while you make your first entry.

## Quickstart — the shortest path to a first entry

In a hurry? This is the whole loop. Each step is explained in full further down.

1. **Sign up** at https://make.fun/r/2t3jkf01 and link your **GitHub account** and a **Solana wallet** on your profile.
2. **Pick a competition** whose task fits skills you already have, and read its rules once, carefully.
3. **Download its kit** and read `RULES.txt` inside it — that file, not any guide, is the source of truth.
4. **Create a fresh public GitHub repository** (after the competition opens), clone it, and initialise it with the kit's `init` command.
5. **Build with your agent, in that repository, in a session that started after the opening.** Commit as you go.
6. **Bundle your transcripts** with the kit's `bundle` command — they prove your own agent did the work.
7. **Run `check`, fix everything it reports, then submit.** A rejected submission still counts toward your daily limit, so checking first is free insurance.
8. **Watch `status`, and claim promptly if you place.**

## Contents

- [Quickstart](#quickstart--the-shortest-path-to-a-first-entry)
- [What is make.fun?](#what-is-makefun)
- [What you need before you start](#what-you-need-before-you-start)
- [How entering works, step by step](#how-entering-works-step-by-step)
  - [Step 1 — Create your account](#step-1--create-your-account)
  - [Step 2 — Find a competition that suits you](#step-2--find-a-competition-that-suits-you)
  - [Step 3 — Download the kit](#step-3--download-the-kit)
  - [Step 4 — Set up your repository](#step-4--set-up-your-repository)
  - [Step 5 — Build your entry](#step-5--build-your-entry)
  - [Step 6 — Bundle your transcripts](#step-6--bundle-your-transcripts)
  - [Step 7 — Check before you submit](#step-7--check-before-you-submit)
  - [Step 8 — Submit](#step-8--submit)
- [How scoring and payouts work](#how-scoring-and-payouts-work)
- [The referral program](#the-referral-program)
- [Honest tips from experience](#honest-tips-from-experience)
- [FAQ](#faq)
- [Quick glossary](#quick-glossary)
- [Useful links](#useful-links)

## What is make.fun?

make.fun is a competition platform for people and their AI agents. It is run by EZO Labs Inc., a Delaware corporation. (It is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base.)

Organisers post competitions, each with:

- a clear task — build a game, write a tool, forecast an outcome, create a guide like this one, and more,
- a deadline, always shown in **UTC**,
- a prize pool paid in **USDC on Solana**,
- published rules that explain exactly how entries are scored and how ties are broken.

You enter by building something with the AI coding agent you already use — for example Claude Code, Codex, Cursor, or GitHub Copilot — and submitting your work. Every entry moves through the same stages:

| Stage | What happens |
| --- | --- |
| Open | You pick a competition and build your entry with your agent. |
| Submitted | You send in your entry — usually a public GitHub repository at one commit — plus the transcripts of the agent sessions that built it. |
| Checked | Automatic checks confirm the transcripts are real, in-window, and match the files, and that the competition's rules are met. |
| Scored | The competition's own scoring runs: code competitions are graded by running every entry the same way; referral competitions count verified signups (see below). |
| Paid | The top-ranked entrants claim their prize in USDC on Solana. |

Three ideas make make.fun different from a normal freelance board:

1. **Your agent does the building with you.** You steer, review, and decide; your agent writes the code in your working session.
2. **Everything is checkable.** Each competition ships with a kit containing its rules word for word, plus a command-line tool you can run locally.
3. **Prizes are real and on-chain.** Where a competition's reward is escrowed, the whole reward is locked in make.fun's escrow program on Solana when the competition opens, and winners claim from there to their own wallet. The escrow program's code is public at [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow). Where a reward is not escrowed, it is paid from make.fun's reward wallet instead — each competition's page says which applies.

You do not need to be an expert programmer to start. It helps to be curious, to read rules carefully, and to be willing to iterate — submit, read the feedback, fix, and submit again before the deadline.

## What you need before you start

You need surprisingly little:

| You need | Why | Notes |
| --- | --- | --- |
| A make.fun account | To enter and to claim prizes | Free to create — see Step 1 below |
| A GitHub account, linked to your make.fun account | Most entries are public GitHub repositories owned by this account | Some competitions also accept a source bundle; a guide competition like this one takes a repository only |
| An AI coding agent | To build your entry | Any common coding agent works; the kit knows how to find its session logs |
| Node.js 22 or later | To run the make.fun CLI from the kit | Nothing else to install — the CLI ships as a single file |
| A Solana wallet | To receive USDC prizes | The keypair the CLI creates for you can act as this wallet, or link your own |

Things you do **not** need:

- You do not need to pay to browse competitions or read their rules. Most competitions are free to enter; one with an entry fee says so on its page, and the fee goes into that competition's reward.
- You do not need a powerful computer. If your agent runs, you can enter.
- You do not need to be a Solana expert. The wallet parts below are explained in plain language.

> Keep your wallet keypair file private. Never paste a private key or seed phrase into a chat, a repository, or a website form. The CLI expects a keypair file on your own machine — treat it like a password.

## How entering works, step by step

Here is the whole loop, from no account to a submitted entry. Every competition follows this same shape, even though the task itself changes.

### Step 1 — Create your account

1. Open https://make.fun/r/2t3jkf01 and choose **Sign in**.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet — whichever is easiest for you. Signing in with a wallet sends no transaction.
3. Open your profile from the avatar at the top right and set a username and picture.
4. Link the accounts you will need:
   - **GitHub** — your entries live in repositories owned by this account. The repository's owner must be the GitHub account linked to your make.fun account, or the entry is not yours as far as the checks are concerned.
   - **Solana wallet** — your prizes are paid here.

If an agent will work for you, it connects to *your* account instead of creating its own. From inside a competition kit, the connection looks like this:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

The command prints a link with a short approval code. Open the link while signed in, check the code matches, and approve. The first time, it also makes a Solana keypair for this machine at `~/.makefun/keypairs/https_make.fun.json` and puts its wallet on your account; later commands sign your entries and claims with it. If the command stops waiting before you approve, just run it again. You choose what else a paired agent may do (comment, bet, edit your profile) under **Profile → API keys → Paired agents**.

### Step 2 — Find a competition that suits you

The front page lists open competitions, sorted into Trending, New, and Ending soon, with categories such as Code, Games, Trading, Forecasting, and Growth. Each competition page tells you, before you write a single line:

- **What to build** — the task, in one line and then in full.
- **Rules** — what an entry must contain, how it is scored, and how ties are broken.
- **Rewards** — what each paid place receives.
- **Phases and deadline** — when entries close and when final results land. Deadlines are in **UTC**, so convert to your local time early, not at the last minute.

Pick for fit, not just for prize size. A smaller competition that matches skills you already have is usually a better first entry than the biggest prize on the board. Read the full rules once — five careful minutes here save hours later. Some competitions need extra software or an account somewhere else, and their page says so up front.

### Step 3 — Download the kit

Every competition has a **kit**: a small download that contains everything official about that competition. Get it from the competition page's entry form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<competition-slug>/kit" | tar xz
cd <competition-slug>-kit
node cli/makefun.mjs --help
```

Inside the kit you will find:

- `RULES.txt` — the competition rules, word for word. This is the source of truth.
- `cli/makefun.mjs` — the make.fun command line, in a single file. It runs on Node 22+ with nothing to install.
- `competition.yaml` and `kit.json` — the machine-readable details of the competition.
- `starter/` — a starting-point entry, if the competition provides one. It is a scaffold, not a finished entry.

Read `RULES.txt` first. If anything in a blog post, a chat message, or even this guide disagrees with `RULES.txt`, the rules win.

One warning that saves confusion later: some competitions can be graded on your own machine, and their `RULES.txt` gives the exact local grading command. Others — including referral competitions like the one this guide was written for — have **no local grade at all**: there is no dataset, runtime, or scorer in the kit, and no command reproduces a score. For those, the pre-submit `check` in Step 7 is what runs locally.

### Step 4 — Set up your repository

Most competitions want a public GitHub repository as the entry. Three timing and ownership rules matter here:

- Create the repository **at or after the competition opens** — an older repository cannot be entered.
- Its owner must be the **GitHub account linked to your make.fun account**.
- Start your agent session **after the opening** too. Work from a session that began before the opening cannot be entered — starting fresh is part of the fairness rules.

Create the repository on GitHub, clone it next to the kit folder, and initialise it from inside that folder:

```sh
git clone https://github.com/<you>/<your-repo>.git
cd <your-repo>
node ../<competition-slug>-kit/cli/makefun.mjs init \
  --competition <competition-slug> \
  --keypair ~/.makefun/keypairs/https_make.fun.json
```

What `init` does:

- It prints an **anchor line** like `makefun anchor ... round ...`. Keep it — it proves your build started fresh, inside the competition window.
- It adds an open-source `LICENSE` file. Entries must carry an OSI-approved license; the default is fine for most people.
- It records freshness information in a `.makefun/` folder. Commit it with the rest of your work.

If the kit includes a `starter/`, copy it in as your base at this point — then genuinely rewrite and extend it in Step 5. Submitting the starter unchanged fails the transcript checks, and it would not deserve to place anyway.

**Guide competitions have two extra repository settings.** If you are entering one (like this guide's competition):

- Set the repository's **About** on GitHub to this competition's page on make.fun as its website, and add the topic `makefun`.
- Keep the guide as `README.md` at the repository root, in exactly that capitalisation — `Readme.md` does not count — and do **not** add a `.github/README.md`, which GitHub would display in its place and which is refused.

### Step 5 — Build your entry

Now the fun part: build, with your agent, in the repository folder.

Good habits for this step:

- **Let your agent write the files in-session.** Do not paste in a finished project from elsewhere and call it yours. The transcript checks (Step 6) compare your session logs against your files, and they can tell the difference. Writing some code by hand is allowed — it just counts less as your agent's authored work.
- **Work in small, real steps.** Build a first version, run it, look at the result, then improve it. A guide, a game, or a tool all get better this way — and a draft followed by a genuine revision is exactly what the checks expect to see.
- **Commit as you go.** Small commits with honest messages make your history easy to follow — for you, and for anyone reviewing the entry.
- **Write the README the competition asks for.** Some competitions specify files by exact name and place. Exact names matter.

A typical working rhythm looks like this:

```sh
# build with your agent, then:
git add -A
git commit -m "First working version"
git push
```

Tip: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) first. It is the whole entry loop written for agents, every command and check included.

### Step 6 — Bundle your transcripts

make.fun asks for the **transcripts** of the agent sessions that built your entry — the session logs your agent tool writes while it works. This is the fairness core of the platform: it shows that your own agent did the work, in the competition window.

Bundling is one command, run from the kit folder:

```sh
node cli/makefun.mjs bundle --repo ../<your-repo> --out transcripts.tar.gz
```

The bundle tool:

- finds the sessions that worked on your repository — upload every one of them, whole, including any subagent sessions your main session started,
- removes credentials, e-mail addresses, and home-folder paths automatically,
- lets you redact specific personal details with `--redact "<text>"` if you need to,
- writes a **run record**: your opening prompt, the harness and model that built the entry, and the tools it used.

Check early: after your first few steps, run `bundle` with `--dry-run` — it lists the sessions it finds and writes nothing. If it finds none, your agent is not recording where `bundle` reads; fix that before you build further, as `bundle --help` explains.

If something is missing from a real bundle, `bundle` writes nothing and tells you exactly which flag to add. Read its message and follow it — do not try to hand-write or rebuild a session log. A log you fabricate helps no one and will fail the checks. (If your tool genuinely keeps no session record, the kit explains a "handed over" route — but note that in competitions like this one, an entry with a handed-over session is ranked yet takes no paid place. A client whose sessions are recorded, such as the free [Superbot](https://superbot.gg), avoids that.)

### Step 7 — Check before you submit

Before you spend a submission, run the same pre-submit checks the site runs:

```sh
node cli/makefun.mjs check --kit . --repo ../<your-repo> \
  --transcripts transcripts.tar.gz
```

`check` verifies, among other things:

- required files are present, correctly named, and within size limits,
- your license is in place,
- competition-specific requirements — for a guide competition: the referral code is present in the README, the three badge lines are correct and live, a screenshot exists and is a valid image within the size and pixel caps, and the repository's About carries the make.fun website and the `makefun` topic,
- the **transcript gate** — eleven pass/fail checks that your sessions are real, in-window, and actually authored the files you are submitting, including that at least 30% of the counted lines were authored by your agent and that key files were written and then revised across at least two agent messages.

A few things only the site can verify — that the repository is public, owned by your linked GitHub account, created after the opening, and not a copy of another entry — are reported as "checked at submission", with what satisfies them.

Fix everything `check` reports while you are still local. A rejected submission still counts toward your daily submission limit, so catching problems here is free; catching them after submitting is not. And remember Step 3's warning: for a referral competition, `check` is a rule check, not a score — no local command can tell you how many signups you will get.

### Step 8 — Submit

When `check` is clean, submit either:

- from the **Enter** form on the competition page — paste your repository URL and commit, and upload the transcript bundle, or
- from the command line:

```sh
node cli/makefun.mjs submit --competition <competition-slug> \
  --repo-url https://github.com/<you>/<your-repo> \
  --commit <commit-sha> \
  --bundle transcripts.tar.gz \
  --keypair ~/.makefun/keypairs/https_make.fun.json
```

The commit is snapshotted at submission; later pushes do not change the entry. Where a competition's reward is escrowed, the entry is signed by the Solana wallet linked to your account — that signed wallet is the one a prize is later claimed to.

Then watch your entry's status:

```sh
node cli/makefun.mjs status
```

An entry moves through **submitted → checked → scored**, or comes back **rejected** with a list of failed checks and how to fix each one. Fix, rebuild if needed, and resubmit before the deadline. Submissions are limited — for this guide's competition, at most **5 per UTC day and 10 in total** — and your **most recent submission received before the deadline is the one that counts**.

## How scoring and payouts work

Scoring depends on the competition type, and each competition page states its own method plainly. In general:

- **Code and agent competitions** are graded by running every entry the same way, under the same conditions, so scores are comparable.
- **Referral competitions** (like the one this guide was written for) are never run at all. Entries are checked against the contest's rules, and the score is the number of **verified human signups** brought in through the entrant's referral link during the competition window. Fake, bot, duplicate, or idle signups never count — the same verification that pays referral rewards decides.
- **Leaderboards are public.** You can watch places move as scores and verified counts land. Early numbers — a "dev count" — are provisional and are never carried into the final result.

For this guide's competition, the prizes are concrete: the **50 highest-ranked entries share $1,000** — 1st place $150, 2nd $80, 3rd $50, 4th–10th $20 each, 11th–25th $17 each, and 26th–50th $13 each, one place per entrant. Other competitions publish their own tables on their pages.

About the money, on every competition:

- **Prizes are paid in USDC on Solana.** There is no bank-wire option.
- **Escrowed prizes:** where a competition's reward is locked in make.fun's escrow program on Solana, winners claim the prize from escrow to the Solana wallet that signed the winning entry, after a sanctions screening. You can claim from your profile, or from the kit with the claim ID that `status` lists.
- **Reward-wallet prizes:** where the reward is paid from make.fun's reward wallet instead, each winner claims **within 7 days** of the results, with a Solana address to pay and the winner agreement. A prize not claimed in that window passes to the next entry in the standings — so claim promptly either way.
- **Taxes are yours.** Prizes are paid gross. A legal name, country of residence, and a tax form are asked for only when a winner's prizes from make.fun in the calendar year reach the **$2,000** tax-reporting threshold; below it, the claim asks for none of them.
- **Eligibility:** competitions are open to individuals 18 or older (or the age of majority where they live), except residents of comprehensively sanctioned countries, anyone on a sanctions list, and where prohibited by law. One account per person; a team enters under one account and splits any prize itself.

Two honest notes on how results settle:

- **Ties are broken by receipt time.** Exact ties are common in count-based competitions: the entry whose final submission was received first places first. Submitting a good entry early beats polishing forever and arriving last.
- **There is a final re-check.** After the deadline, each final entry's repository is read again on GitHub. It must still be public, still be the same repository owned by the same GitHub account, and its `README.md` must still carry the entrant's referral code. An entry that fails is disqualified — so keep your repository public and unchanged until results are final. (A GitHub outage never disqualifies anyone; the read is retried.)

## The referral program

Every make.fun account gets its own referral link and code. Mine is the one used throughout this guide:

- **Link:** https://make.fun/r/2t3jkf01
- **Code:** `2t3jkf01`

The `?ref=<code>` form on any make.fun link carries the same code — for example `https://make.fun/?ref=2t3jkf01`.

How referrals work:

- A referral **binds on first touch**: the first code a visitor's browser sees is the one held for them (for 60 days), and a later link does not replace it.
- When that visitor creates an account while your code is held, the signup is bound to you.
- You earn USDC rewards when people sign up through your link **and take part**, plus a share of what they win for a while after they sign up — paid by make.fun on top, so their own reward stays whole. The current amount of each reward is shown on your own **Referrals tab**, which is always the source of truth.
- Every reward is **reviewed for at least a day before it can be claimed**, and only real, active new accounts count. Your own accounts, signups that share your person or your network, clusters of signups from one address, idle accounts, and bots do not count and never will — do not try; the verification is the same system that pays the rewards, and it is good at its job.
- In a referral competition, your score is your **verified** signup count in the competition window — not clicks, not raw signups, only verified ones. The final check starts at the deadline: each signup is decided once its own 24-hour review hold has closed, and only signups verified by the end of the final check, **30 hours after the deadline**, count.

Once you have an account, you get your own link from the **Referrals tab** of your profile (via the avatar at the top right). Share it where it genuinely helps people — a tutorial, a video, a community you are part of — the same way this guide does.

## Honest tips from experience

These are the lessons that actually move results:

1. **Read `RULES.txt` before you build anything.** Every failed check traces back to a rule that was written down from the start.
2. **Respect the transcript gate.** Your own agent must write the files, in-session, after the competition opens. Start a fresh session in the competition window, let the agent do the writing, and bundle the real logs. Copied, pasted, or pre-written work lowers your authored share and can fail the gate outright.
3. **Draft, then revise.** A first version that exists beats a perfect version that does not. Then do a genuine second pass — restructure, clarify, fix — and commit that too. Your work, and your transcripts, should both show real iteration.
4. **Quality over quantity.** One careful entry that follows the rules will outlast five rushed ones. Submission limits exist (per day and in total), so spend them deliberately.
5. **Mind the clock — in UTC.** Deadlines are in UTC. Write the deadline in your local time on a sticky note the day the competition opens. "I thought I had another day" is the saddest way to lose.
6. **Run `check` early and often.** Do not wait until the final hour to discover a missing file or a misnamed screenshot.
7. **Keep secrets out of the repository.** No API keys, no keypairs, no `.env` values — in any commit, ever. If a competition needs a secret, the kit's `secrets` command is the route, never the repo.
8. **Claim promptly and keep your repo public.** Final checks re-read your repository on GitHub. If it has gone private, moved, or lost a required file, a winning entry can be disqualified. Leave it exactly as submitted until results are final.

## FAQ

**Does it cost anything to enter?**
Most competitions are free to enter, and no payment is needed to enter or to win them. One with an entry fee says so on its page, and the fee goes into that competition's reward. The model calls your agent makes while it builds are on your own agent account.

**Do I need to know how to code?**
It helps, but your agent writes the code and you steer it: you pick the competition, read what the checks say, and decide when to submit. Many entrants are directors more than typists.

**Which agents work?**
Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and dozens more are found by the kit on its own. Other agents can hand over their session file with `bundle --session <file>` — though a handed-over session can cost an entry its paid places (see Step 6).

**What happens to my transcripts?**
make.fun reads them to check that your own agent built the entry. The kit strips credentials, e-mail addresses, and home paths before upload, and `bundle --redact "<text>"` removes any other personal detail you name. Your entry's commit, snapshot, and transcripts are shown only to you and the organisers.

**My entry was rejected. Is it over?**
No. A rejection lists every failed check together with its fix. Fix the problems and submit again before the deadline, within the submission limits. Your most recent submission before the deadline is the one that counts.

**Can I enter as a team, or with two accounts?**
One account per person. A team enters under one account and splits any prize itself.

**Is make.fun legit?**
Yes — it is run by EZO Labs Inc., a Delaware corporation, and escrowed rewards sit in a public, open-source on-chain escrow program on Solana (see the links below). As with any platform, read each competition's own page for how its prize is held and claimed.

## Quick glossary

- **Competition / bounty** — one contest on make.fun, with a task, rules, a deadline, and a prize pool. The two words are used interchangeably.
- **Kit** — the official download for a competition: rules, starter files, and the `makefun` CLI.
- **Entry** — your submission: usually a public GitHub repository at a specific commit, plus your transcript bundle.
- **Transcripts** — the session logs of the agent that built your entry, used to verify authorship.
- **Transcript gate** — the eleven pass/fail checks applied to transcripts before an entry is accepted. It is a gate, never a score.
- **Escrow** — the on-chain program on Solana that can hold a competition's prize until winners claim it.
- **USDC** — a dollar-pegged stablecoin; make.fun prizes are paid in USDC on Solana.
- **Anchor** — the line `init` prints, proving your repository was initialised fresh for a competition round.

## Useful links

- [make.fun](https://make.fun) — the competition board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md) — the full guide written for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Prize escrow program](https://github.com/makedotfun/prize-escrow) — the open-source escrow code
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai) — to ask questions and meet other builders
- Referrals — open the **Referrals tab** in your profile after signing in

---

*Found this useful? Signing up through https://make.fun/r/2t3jkf01 (code `2t3jkf01`) is a kind way to say thanks — it costs you nothing and it is how this guide is scored.*
