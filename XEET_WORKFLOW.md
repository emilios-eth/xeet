# Xeet Protocol — Workflow Overview

> **Live PoC:** [emilios-eth.github.io/xeet](https://emilios-eth.github.io/xeet/)

---

## What is Xeet?

Xeet is a protocol that connects **Brands** (sponsors) with **Xeet Certified Creators (XCCs)** — high-signal operators who run coordinated squads of participants to deliver verifiable outcomes. Brands fund bounties with escrowed budgets. XCCs compete to fulfill them by mobilizing their squads. Every outcome is verified on-chain or server-side. Payouts unlock at milestones.

There are two sides to the platform:

---

## 1. Brand / Sponsor Flow

The Brand flow is a 7-step wizard that takes a sponsor from naming their campaign to watching live results.

### Step 1 — Brand Name

The brand enters their project name. This becomes the campaign identifier visible to all XCCs and participants.

### Step 2 — Define Outcomes (KPIs)

The brand selects one or more verifiable KPIs from a predefined set:

| KPI | Verification Method | Avg Cost | Participant Affinity |
|-----|---------------------|----------|----------------------|
| App Installs | S2S Postback (MMP) | ~$12.50/install | Social-heavy |
| Purchases | S2S Postback | ~$28/purchase | Capital-leaning |
| Sign-ups | S2S / API | ~$6.50/sign-up | Social-heavy |
| On-chain Actions | Contract Indexing | ~$15/tx | Capital-heavy |
| Wallet Connections | On-chain | ~$5/connection | Capital-leaning |
| Content Submissions | Manual + AI | ~$18/submission | Social-heavy |

For each selected KPI, the brand sets a **target** (e.g., 2,000 installs, 5,000 wallet connections).

Once targets are set, the platform surfaces:

- **Platform Intelligence** — estimated squads needed, total members, and a suggested budget based on historical cost-per-outcome.
- **Bounty Profile Analysis** — a social-reach vs. capital-active affinity breakdown. This tells the brand what kind of participants their KPI mix attracts (audience-driven vs. DeFi-native).
- **Integration Requirements** — the exact technical setup needed per KPI (MMP postback URLs, contract addresses, webhook schemas, etc.). The bounty cannot go live until all endpoints are verified.

### Step 3 — Budget & Milestones

The brand sets:

- **Vault size** (total USDC budget to escrow)
- **Campaign duration** (7, 14, 21, or 30 days)
- **Milestone ladder** (2–6 milestones)

Each milestone has two values:
- **KPI %** — the percentage of total outcomes that must be reached
- **Payout %** — the percentage of the vault that unlocks at that threshold

Example: Milestone 3 at 85% KPI completion unlocks 88% of the vault. This non-linear payout curve rewards campaigns that push past the early milestones.

### Step 4 — Participation Mode

The brand chooses how XCCs can join:

- **Open (FCFS)** — any eligible XCC can accept and start delivering immediately.
- **Filtered** — the brand can set minimum tier, win rate, or category requirements.

### Step 5 — Brand Context

The brand provides public-facing info: website, X handle, and a product description. This is what XCCs and squad members see when evaluating the bounty.

### Step 6 — Review & Checkout

A full summary of the campaign configuration. On confirmation, a checkout modal appears showing:

- **Vault amount** (escrowed, released only on verified outcomes)
- **Platform fee** ($5,000 for verification, disputes, and settlement)
- **Total in USDC**
- **Destination wallet**

Funding locks the campaign parameters.

### Step 7 — Live Dashboard (Brand POV)

After funding, the brand sees a real-time campaign dashboard:

- **KPI counters** — animated, live outcome counts per KPI
- **Milestone tracker** — which milestones have been reached and how much USDC has been unlocked
- **Attribution tree** — a hierarchical view showing which XCC (and which squad members under them) are driving outcomes, with percentage contribution per node
- **Live feed** — a real-time event stream of verified actions (installs, wallet connections, etc.) attributed to specific participants

---

## 2. XCC (Certified Creator) Flow

The XCC flow is a 4-step journey from browsing bounties to managing a live campaign.

### Step 1 — Profile & Bounty Board

The XCC lands on their profile card showing:

- **Tier** (e.g., Elite)
- **Squad size** and active count
- **Historical alpha (α)** — the average share of rewards passed to their squad
- **Win rate, total outcomes, and total capital earned**
- **Campaign count**

Below the profile is the **Bounty Board** — a grid of all open bounties. Each card shows:

- Brand name, logo, and category
- Vault size
- KPI targets (with icons)
- Duration and participation mode (Open vs. Filtered)
- **Squad estimates** — how many squads and members the bounty likely needs, based on historical data
- **Coverage %** — how much of the estimated member requirement the XCC's current active squad can cover. This is the key signal: high coverage = strong fit.

### Step 2 — Bounty Detail

When an XCC clicks into a bounty, they get a deep breakdown:

- **Vault size, estimated squads, and their personal coverage**
- **Per-KPI analysis**: squads needed, avg cost per outcome, and a projection of how many outcomes the XCC's squad can deliver based on their active member count
- **Milestone ladder**: the full payout schedule showing USDC amounts at each threshold

This is where the XCC decides whether the bounty is worth pursuing given their squad composition.

### Step 3 — Configure Offer (Alpha & Economics)

This is the core economic decision. The XCC sets their **alpha (α)** — the percentage of earned rewards shared with the squad.

- A slider ranges from 10% to 50%
- The UI shows a real-time split: **XCC take** vs. **Squad pool** vs. **Per-member payout**
- An **Alpha Strategy** advisor gives contextual guidance based on the selected value and the XCC's historical average

Key details on this screen:

- **Squad Readiness** panel — active count, activation rate, coverage %, and recommended sub-XCC count
- **Card Commitment** — squad members must commit one of their held Creator Cards to participate. Each member can only commit to one XCC per bounty (but can join multiple bounties under different XCCs). The card locks on acceptance and unlocks at settlement.

Alpha is **public and permanent** for the campaign. It becomes part of the XCC's on-chain reputation.

### Step 4 — Live Dashboard (XCC POV)

After submitting the offer, the XCC sees their campaign dashboard:

- **KPI progress bars** — animated progress toward each target with percentage and count
- **Your Take vs. Squad Pool** — real-time USDC split based on unlocked milestones and the committed alpha
- **Milestone tracker** — which thresholds have been hit
- **Attribution tree** — the XCC is highlighted ("YOU") at the root, with sub-XCCs and individual fans branching below, each showing their outcome count and percentage contribution
- **Live feed** — same real-time event stream as the brand sees, but with the XCC's own actions highlighted in purple

---

## Key Concepts

| Concept | Description |
|---------|-------------|
| **Vault** | Escrowed USDC budget. Released only on verified outcomes. |
| **Alpha (α)** | The % of rewards an XCC shares with their squad. Public and permanent per campaign. |
| **Squad** | A group of participants coordinated by an XCC. Members commit a Creator Card to join. |
| **Attribution Tree** | Hierarchical view of who drove which outcomes. XCC → Sub-XCCs → Fans. |
| **Milestones** | Non-linear payout thresholds. Reaching 85% of KPIs might unlock 88% of the vault. |
| **Coverage** | How much of a bounty's estimated member requirement an XCC's squad can fulfill. |
| **Creator Card** | Held by squad members. Committed to one XCC per bounty. Locks on accept, unlocks at settlement. |
| **KPI Affinity** | Whether a bounty's KPI mix favors social-reach participants or capital-active ones. |
| **Bounty Profile** | The weighted social vs. capital split across all selected KPIs. |
