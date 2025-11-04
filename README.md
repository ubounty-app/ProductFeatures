# ProductFeatures
Documentation for Ubounty.ai Product


# Ubounty Payment Logic - Business Documentation

## Overview

This document explains how payments work on Ubounty from a business and user perspective. It covers what happens when developers solve issues, how bounty creators allocate funds, and when payments are executed.

---

## Core Concepts

### What is a Bounty?

A bounty is a cryptocurrency reward (paid in USDC) offered by a project maintainer or sponsor for solving a specific GitHub issue. The funds are locked in escrow when the bounty is created and released when the work is completed and approved.

### Multiple Developers Can Contribute

Unlike traditional bounties where only one person can claim the reward, Ubounty allows multiple developers to contribute to solving the same issue. The bounty creator decides how to split the payment among all contributors.

### Payment is Automatic

Once the bounty creator decides how to allocate funds, payments happen automatically. If a developer has connected their wallet, they receive payment immediately. If not, the payment waits until they connect their wallet, then executes automatically.

---

## The Complete Payment Journey

### Stage 1: A Pull Request Gets Merged

**What Happens:**

When a developer's code contribution (Pull Request) is merged by the repository maintainer, Ubounty automatically detects this event and records it.

**Important Notes:**

- The developer must include "Fixes #123" (or similar keywords) in their PR description so the system knows which issue it solves
- Multiple PRs can be merged for the same issue over time
- Each PR merge triggers a new notification to the bounty creator
- The system tracks all merged PRs until the bounty creator makes a payment decision

**Notification:**

The bounty creator receives a GitHub comment on the issue after each PR merge:
```
🎯 Pull Request Merged!

@bounty_creator Another pull request has been merged for this bounty!

PR Details:
- PR #42 - Fix memory leak in useEffect
- Author: @developer_alice
- Merged: January 15, 2025

Total PRs merged for this issue: 2

💰 Payment Decision Required
Review all PRs and decide payment allocation
Total Bounty: $100 USDC

⏰ Deadline: January 22, 2025
If no decision by deadline, payment will be split evenly.
```

**Timeline:**

- A 7-day countdown begins from the first PR merge
- Additional PRs can merge during this period
- All merged PRs are included in the payment decision

### Stage 2: Bounty Creator Decides Payment

**What the Creator Sees:**

The bounty detail page shows all merged PRs, grouped by developer:
```
Payment Decision for Issue #123
Total Bounty: $100 USDC

Merged Pull Requests:

┌────────────────────────────────────┐
│ @developer_alice                   │
│ Contributed: PR #42, PR #47        │
│ Payment allocation: [___]%         │
└────────────────────────────────────┘

┌────────────────────────────────────┐
│ @developer_bob                     │
│ Contributed: PR #45                │
│ Payment allocation: [___]%         │
└────────────────────────────────────┘

Total: 0% (must equal 100%)

[Confirm Payment Decision]
```

**Decision Rules:**

- Percentages must add up to exactly 100%
- The creator enters one percentage per developer (not per PR)
- A developer who submitted multiple PRs receives one combined payment
- The creator can allocate 0% to reject a developer's contribution
- Once submitted, the decision cannot be changed

**Example:**

Bounty: $100
- Developer Alice contributed 2 PRs → Assigned 70% → Receives $70
- Developer Bob contributed 1 PR → Assigned 30% → Receives $30

### Stage 3: Payment Execution

**Scenario A: Developer Has Wallet Connected**

If the developer already connected their cryptocurrency wallet in settings:

1. Payment executes immediately after the creator's decision
2. USDC transfers from escrow to the developer's wallet
3. Transaction completes in 3-5 seconds
4. A GitHub comment confirms payment with the transaction link
5. Developer can verify payment on blockchain explorer

**Scenario B: Developer Has No Wallet**

If the developer hasn't connected a wallet yet:

1. Payment is approved but not yet executed
2. Status marked as "awaiting wallet"
3. Developer receives a GitHub notification:
```
💰 Payment Approved!

@developer_alice Your contribution has been approved for payment!

Amount: $70 USDC (70%)

To receive payment, connect your wallet:
→ Visit https://ubounty.ai/settings

Once you add a wallet address, payment will be sent automatically.
```

4. When the developer later visits settings and connects their wallet, payment executes automatically within seconds

**Important:** There is no deadline for connecting a wallet. The approved payment waits indefinitely until the developer claims it.

### Stage 4: Auto-Split (If Creator Doesn't Decide)

**What Happens:**

If the bounty creator doesn't make a payment decision within 7 days of the first PR merge, the system automatically splits the bounty evenly among all merged PRs.

**Example:**

Bounty: $100
- PR #42 by Alice → Receives $33.33
- PR #45 by Bob → Receives $33.33  
- PR #47 by Alice → Receives $33.34

Total for Alice: $66.67 (two PRs)
Total for Bob: $33.33 (one PR)

**Process:**

1. System identifies bounties past the 7-day deadline
2. Calculates equal split: 100% ÷ number of PRs
3. Creates payment decisions automatically
4. Executes payments for developers with wallets
5. Marks others as "awaiting wallet"
6. Posts notification on GitHub explaining the auto-split

**Why This Exists:**

This protects developers from indefinite waiting. If a bounty creator abandons the decision process, developers still get paid fairly.

---

## Special Scenarios

### Same Developer, Multiple PRs

**Situation:** 

A developer submits multiple PRs that all get merged for the same issue.

**Handling:**

- UI groups all PRs under the developer's name
- Bounty creator assigns one percentage to the developer
- The developer receives a single combined payment
- Behind the scenes, the percentage is split evenly across their PRs for record-keeping

**Example:**

Alice submits PR #42 and PR #47 (both merged)
Creator assigns Alice 70%
Alice receives one payment of $70 (not two separate payments of $35 each)

### Late PRs After Payment Decision

**Situation:**

The bounty creator makes a payment decision, then another PR gets merged afterward.

**Handling:**

- The late PR is ignored
- No payment allocated to it
- The bounty is considered closed after the first payment decision
- This prevents reopening settled bounties

**Why:**

Payment decisions are final. Once funds are allocated, the bounty is closed to new contributions. This provides finality for both creators and developers.

### Rejecting Contributions

**Situation:**

The bounty creator believes a merged PR doesn't adequately solve the issue.

**Options:**

1. **Allocate 0%**: Give the developer 0%, effectively rejecting their contribution
2. **Partial Credit**: Give them a small percentage (e.g., 10%) as acknowledgment
3. **Split Among Others**: Ignore the rejected PR and allocate 100% among other developers

**Important:** Even if a PR is merged by the repository maintainer, the bounty creator has final say on whether it deserves payment.

### Developer Never Claims Payment

**Situation:**

Payment is approved but the developer never connects a wallet.

**Handling:**

- Payment remains in "awaiting wallet" status indefinitely
- Funds stay in escrow (earning yield for the platform)
- Developer can claim at any time in the future (no deadline)
- After 2 years of inactivity, the platform may reclaim unclaimed funds

**Philosophy:**

The platform acts as custodian of unclaimed funds. There's a small cost to hold funds safely (security, monitoring, compliance), so the platform benefits from the USDC yield on unclaimed balances.

---

## Payment Timeline Examples

### Example 1: Single Developer, Immediate Payment

**Day 1:** Bounty created for $50

**Day 3:** Developer Alice merges PR #42
- GitHub comment notifies creator
- 7-day decision countdown begins

**Day 5:** Creator decides payment
- Alice: 100%
- Alice already has wallet connected
- Payment executes immediately: $50 → Alice's wallet
- Transaction confirmed in 5 seconds
- GitHub comment posted with transaction link

**Outcome:** Total time from PR merge to payment: 2 days

---

### Example 2: Multiple Developers, Mixed Wallet Status

**Day 1:** Bounty created for $100

**Day 3:** Developer Alice merges PR #42
- GitHub comment notifies creator
- 7-day countdown starts

**Day 5:** Developer Bob merges PR #45
- Second GitHub comment posted
- Countdown continues (deadline still Day 10)

**Day 6:** Developer Alice merges PR #47
- Third GitHub comment posted
- Total: 3 PRs from 2 developers

**Day 8:** Creator decides payment
- Alice (PR #42, #47): 70% = $70
- Bob (PR #45): 30% = $30

**Immediate results:**
- Alice has wallet → Paid $70 instantly
- Bob has no wallet → Marked as "awaiting wallet"
- Bob receives GitHub notification to add wallet

**Day 12:** Bob connects wallet
- Automatic payment of $30 executes
- Bob receives GitHub confirmation
- Bounty now fully paid

**Outcome:** Alice paid in 5 days, Bob paid in 9 days

---

### Example 3: Auto-Split Scenario

**Day 1:** Bounty created for $90

**Day 4:** Developer Alice merges PR #42
- 7-day countdown starts (deadline: Day 11)

**Day 6:** Developer Bob merges PR #45

**Day 8:** Developer Carol merges PR #50

**Day 11:** Deadline passes, no decision from creator
- Auto-split triggered
- 3 PRs total → Each gets 33.33%
- Alice: $30
- Bob: $30
- Carol: $30

**Day 11 (continued):**
- Alice has wallet → Paid $30 immediately
- Bob has wallet → Paid $30 immediately
- Carol has no wallet → Marked "awaiting wallet"

**Day 15:** Carol connects wallet
- Automatic payment of $30 executes

**Outcome:** Auto-split protected all developers from indefinite waiting

---

## User Roles and Responsibilities

### Bounty Creator Responsibilities

1. **Create Clear Issues**: Write detailed GitHub issues so developers know what to build
2. **Set Appropriate Amounts**: Price bounties fairly based on complexity
3. **Review PRs Promptly**: Don't let PRs sit without feedback
4. **Make Fair Payment Decisions**: Allocate percentages based on actual contribution quality
5. **Decide Within 7 Days**: Avoid auto-split by reviewing PRs within the deadline

### Developer Responsibilities

1. **Reference Issues Properly**: Include "Fixes #123" in PR descriptions
2. **Submit Quality Code**: Maintainers won't merge low-quality work
3. **Connect Wallet Early**: Add wallet in settings to receive instant payment
4. **Communicate in GitHub**: Announce you're working on an issue to avoid duplicate effort
5. **Accept Decisions Gracefully**: Bounty creator has final say on payment allocation

### Repository Maintainer Responsibilities

1. **Merge Quality PRs**: Only merge code that actually solves the issue
2. **Review Promptly**: Don't let PRs sit for weeks
3. **Be Fair**: Don't favor friends or discriminate against contributors
4. **Close Issues**: Close the issue when all PRs are merged and work is done

---

## Payment Security & Trust

### Funds Are Safe in Escrow

- All bounty funds are locked on the blockchain when created
- Platform cannot spend funds without creator approval
- Funds are held in USDC stablecoin (1:1 with US Dollar)
- Blockchain transactions are publicly verifiable

### Payment Decisions Are Final

- Once creator confirms allocation, it cannot be reversed
- This protects both creators and developers from disputes
- All decisions are recorded with timestamps
- GitHub comments provide public audit trail

### No Chargebacks

- Cryptocurrency payments cannot be reversed
- Developers receive irreversible payments
- Creators must carefully review PRs before approving
- This is fundamentally different from traditional payment platforms

### Platform Fees

- 5% platform fee charged when bounty is created
- No additional fees on payouts
- Gas fees paid by platform using Coinbase Paymaster
- Developers receive 100% of their allocated amount

---

## Frequently Asked Questions

**Q: Can a bounty creator change their payment decision after submitting?**

No. Payment decisions are final. Once confirmed, payments execute immediately (or wait for wallet connection) and cannot be altered.

**Q: What if two developers submit nearly identical solutions?**

The repository maintainer decides which PRs to merge. The bounty creator then decides how to allocate payment among all merged PRs. They could give equal amounts, favor the first/better submission, or any other distribution that totals 100%.

**Q: Can a developer work on a bounty without claiming it first?**

Yes. There is no "claiming" mechanism. Developers simply submit PRs. Only merged PRs are eligible for payment. This encourages quality over speed.

**Q: What happens if the repository maintainer merges a spam PR?**

The bounty creator can allocate 0% to that PR, effectively rejecting it. The maintainer's merge decision is separate from the payment decision.

**Q: How long does a blockchain payment take?**

Typically 3-5 seconds on Base network. The transaction is confirmed almost instantly. Developers can see it in their wallet within seconds.

**Q: Can a developer change their wallet address after payment is approved?**

No. Once a payment decision is made, the wallet address is locked. If the developer changes their wallet in settings afterward, the payment still goes to the original address.

**Q: What if a developer's wallet address is wrong?**

Cryptocurrency transactions are irreversible. If payment goes to a wrong address, it cannot be recovered. Developers must double-check their wallet address before connecting it.

**Q: Can a bounty be canceled after PRs are merged?**

No. Once a PR is merged, the bounty is locked. The creator must either make a payment decision or wait for auto-split. Funds cannot be refunded once PRs are merged.

**Q: What if the bounty creator never makes a decision and never logs in?**

After 7 days, auto-split executes. Developers get paid evenly regardless of creator activity. The platform protects developers from abandonment.

**Q: Can a developer see how much they'll receive before wallet connection?**

Yes. The GitHub comment tells them the exact amount approved for payment. They know before connecting their wallet.

**Q: Is there a minimum bounty amount?**

Yes, $10 minimum. Below that, blockchain transaction fees would consume too much of the payout to be worthwhile.

---

## Platform Philosophy

### Fairness

Multiple developers can contribute, and all can be rewarded proportionally. This encourages collaboration over competition.

### Transparency  

All PRs, merges, and payment decisions are visible on GitHub. Nothing happens in private. The community can see who contributed what and how payment was allocated.

### Automation

Once a decision is made, technology handles the rest. No manual wire transfers, PayPal requests, or payment coordination needed.

### Protection

The 7-day auto-split protects developers from negligent or absent bounty creators. Developers will get paid fairly even if creators disappear.

### Finality

Decisions are permanent. This provides closure. Once paid, the bounty is done. No lingering disputes or renegotiations.

---


