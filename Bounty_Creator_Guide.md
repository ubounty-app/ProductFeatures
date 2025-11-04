# Bounty Creator Guide

## Overview

This guide covers everything you need to create and manage bounties on Ubounty.ai.

---

## Table of Contents

1. [Before You Start](#before-you-start)
2. [Creating a Bounty](#creating-a-bounty)
3. [AI-Powered Analysis](#ai-powered-analysis)
4. [Making Payment Decisions](#making-payment-decisions)
5. [Managing Bounties](#managing-bounties)
6. [Troubleshooting](#troubleshooting)

---

## Before You Start

### What You Need

1. **GitHub Account** - For OAuth login
2. **Crypto Wallet** - MetaMask, Coinbase Wallet, or Rainbow with Base network support
3. **USDC on Base** - Fund your bounties

### Cost Structure

**Platform Fee: 5%**

| Bounty | Fee | Total You Pay | Developer Gets |
|--------|-----|---------------|----------------|
| $10    | $0.50 | $10.50      | $10            |
| $100   | $5.00 | $105.00     | $100           |
| $500   | $25.00 | $525.00    | $500           |

Minimum: $10 USDC

---

## Creating a Bounty

### Step 1: Login

Visit [ubounty.ai](https://ubounty.ai) → "Create Bounty" → Login with GitHub

### Step 2: Select Issue

Paste GitHub issue URL:
```
https://github.com/owner/repo/issues/123
```

**Requirements:**
- Issue must be **open**
- Repository must be **public**
- You need comment permission

### Step 3: Review AI Analysis

AI provides:
- Pricing suggestion ($min - $max)
- Required skills
- Time estimate
- Difficulty level
- Auto-generated requirements

You can accept or modify these suggestions.

### Step 4: Configure Details

**Bounty Amount** (Required)
- Set USDC amount
- Platform calculates 5% fee automatically

**Description** (Optional)
- Add context or specific requirements

**Tags** (Optional)
- JavaScript, React, Python, etc.

**Deadline** (Optional)
- Target completion date (not enforced)

### Step 5: Review & Fund

Review summary:
```
Bounty: $100
Platform Fee: $5
Total: $105
```

Click "Fund & Create Bounty":
1. Connect wallet (if first time)
2. Approve USDC transaction
3. Wait 3-5 seconds for confirmation

### Step 6: Bounty Goes Live

Automatically:
- GitHub comment posted on issue
- Listed on ubounty.ai/bounties
- Transaction hash recorded
- Ready for developers

**Timeline:** 10-20 seconds from payment to live

---

## AI-Powered Analysis

### What AI Analyzes

**Issue Content:**
- Title and description
- Code context
- Labels and comments

**AI Output:**
- Pricing range with reasoning
- Required technologies
- Difficulty assessment
- Structured requirements
- Acceptance criteria

### When to Override AI

**Adjust Higher:**
- Time-sensitive work
- Specialized expertise needed
- Critical bug/feature

**Adjust Lower:**
- Good learning opportunity
- Not urgent
- Testing the platform

---

## Making Payment Decisions

### When You Decide

**Trigger:** PR merged that references your bounty issue

**Timeline:**
- Day 0: First PR merged
- Days 1-7: Decision window
- Day 7: Auto-split if no decision

### Decision Interface

You'll see all merged PRs grouped by developer:

```
Payment Decision Required
Total Bounty: $100 USDC

Developer: @alice
PRs: #42, #47
Allocate: [___]% → $0

Developer: @bob
PRs: #45
Allocate: [___]% → $0

Total: Must equal 100%
```

### Allocation Rules

- Must total exactly 100%
- One percentage per developer (not per PR)
- Minimum: 0% (to reject)
- Maximum: 100% (single winner)
- Decimals allowed (e.g., 33.33%)

### Decision Examples

**Single Developer:**
```
@alice: 100% → $100
```

**Split Contribution:**
```
@alice (core fix): 70% → $70
@bob (tests): 30% → $30
```

**Rejecting Poor Work:**
```
@alice (complete): 100% → $100
@bob (inadequate): 0% → $0
```

### After Confirmation

**Payment decisions are final.**

- Developers with wallets: Paid in 3-5 seconds
- No wallet: Payment approved, waiting for wallet connection
- GitHub comment posted with details
- Bounty closed

### Auto-Split Protection

If you don't decide within 7 days:
- Payment splits equally among all merged PRs
- Same developer with multiple PRs gets combined payment
- Automatic execution, no reversal

---

## Managing Bounties

### Your Dashboard

Access at **ubounty.ai/my-bounties**

**Active Bounties:**
- Status and views
- PR activity
- Deadline countdown

**Pending Decisions:**
- PRs awaiting allocation
- Days remaining
- Quick action link

**Completed:**
- Payment history
- Transaction hashes

### Monitoring

**GitHub Notifications:**
- PR merged → Comment posted
- Payment decision deadline approaching
- Auto-split executed

**Dashboard Alerts:**
- New PR activity
- Decision deadline in 24 hours

---

## Troubleshooting

### Bounty Not on GitHub

**Check:**
- Wait 30-60 seconds
- Verify comment permissions
- Check GitHub issue exists

**Fix:** Contact support with bounty ID

### Can't Edit Bounty

**After funding:** Amount is locked

**Solution:** Create new bounty if needed to adjust

### Payment Failed

**Common Issues:**
- Insufficient USDC balance → Add funds, retry
- Wrong network → Switch to Base
- Transaction rejected → Approve in wallet

### No One Working

**Try:**
- Increase amount
- Clarify requirements
- Extend deadline
- Share in dev communities

---

## Best Practices

### Creating Effective Bounties

**Clear Requirements:**
- Detailed issue description
- Specific acceptance criteria
- Examples or mockups

**Appropriate Pricing:**
- $10-50: Simple fixes
- $50-200: Medium features
- $200+: Complex work

**Responsive:**
- Answer questions quickly
- Make payment decisions within 2-3 days
- Acknowledge good work

### Fair Payment Decisions

**Consider:**
- Quality of contribution
- Scope of work
- Timing (first vs best)
- Multiple PRs from same developer

**Communicate:**
- Explain 0% allocations
- Recognize partial contributions
- Be consistent

---

## Common Questions

**Can I cancel a bounty?**
Before PRs merged: Contact support
After PRs merged: No, must allocate payment

**What if maintainer merges low-quality PR?**
You control payment - can allocate 0%

**Can I change my decision?**
No, payment decisions are final

**Multiple PRs from same person?**
Allocate one percentage, they get combined payment

---

## Next Steps

- **Payment Details:** [Payout Logic](./Payout_logic.md)
- **Security Info:** [Payment & Security](./Payment_Security.md)
- **All Features:** [Platform Features](./Platform_Features.md)
- **Questions:** [FAQ](./FAQ.md)

---

**Need Help?**
- Docs: This repository

---

