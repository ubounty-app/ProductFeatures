# Developer Guide - Earning Bounties

## Overview

Learn how to find bounties, submit quality work, and receive cryptocurrency payments.

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Finding Bounties](#finding-bounties)
3. [Submitting Solutions](#submitting-solutions)
4. [Getting Paid](#getting-paid)
5. [Maximizing Earnings](#maximizing-earnings)
6. [Troubleshooting](#troubleshooting)

---

## Getting Started

### What You Need

1. **GitHub Account** - To submit PRs
2. **Crypto Wallet** - MetaMask, Coinbase Wallet, or Rainbow (for receiving USDC)
3. **Technical Skills** - Ability to solve the issue

**You don't need any crypto to start** - you're receiving payment, not sending it!

### How Payment Works

1. Submit PR → Maintainer merges
2. Creator reviews (up to 7 days)
3. Creator allocates payment %
4. USDC arrives in your wallet (3-5 seconds)

**Payment Currency:** USDC (stablecoin, 1 USDC = $1 USD)

---

## Finding Bounties

### Browse Ubounty

Visit [ubounty.ai/bounties](https://ubounty.ai/bounties)

**Filter by:**
- Programming language
- Bounty amount ($10 - $1000+)
- Difficulty (beginner, intermediate, advanced)
- Deadline

**Sort by:**
- Newest
- Highest paying
- Ending soon

### Find on GitHub

Look for bounty comments on GitHub issues:

```
🎯 Bounty Available!
$100 USDC bounty on this issue

View details: ubounty.ai/bounty/owner/repo/123
```

### Evaluate Before Starting

**Check:**
- Can you solve it? (skills match)
- Is payment worth time? (calculate hourly rate)
- Are requirements clear?
- Is deadline realistic?

**Red flags:**
- Vague requirements
- Unrealistic timeline
- Very low amount for complexity
- Inactive repository

---

## Submitting Solutions

### Step 1: Work on Issue

**Best Practice:** Comment on issue that you're working on it

```
Hi! I'm working on this issue.
Expected to submit PR by [date].
```

### Step 2: Implement Solution

1. Fork repository
2. Create branch
3. Implement fix
4. Write tests
5. Update documentation

**Quality checklist:**
- ✓ Solves the issue completely
- ✓ All tests pass
- ✓ Follows repository style
- ✓ No debug code left
- ✓ Documentation updated

### Step 3: Create Pull Request

**CRITICAL:** PR description must include:
```
Fixes #123
```

Alternative keywords:
- `Closes #123`
- `Resolves #123`

**Good PR description:**
```
## Fixes
Fixes #123

## Changes
- Fixed memory leak in component
- Added tests for edge cases
- Updated documentation

## Testing
- All tests pass
- Manually tested in Chrome/Firefox
```

### Step 4: Address Review Feedback

- Respond to comments promptly
- Make requested changes
- Be professional
- Push updates to same branch

---

## Getting Paid

### Payment Timeline

```
PR Merged → Creator Decides (0-7 days) → Payment Executes
```

**Best case:** 2-3 days
**Typical:** 3-5 days
**Maximum:** 7 days (auto-split)

### Payment Scenarios

**Scenario A: You Get 100%**

You solved it alone:
```
@you: $100 (100%)
```

**Scenario B: Split Payment**

Multiple contributors:
```
@you (core fix): $70 (70%)
@other (tests): $30 (30%)
```

**Scenario C: Multiple PRs**

You submitted multiple PRs:
```
@you (PR #42, #47): $85 (85%)
Combined payment for all your work
```

**Scenario D: Auto-Split**

Creator didn't decide in 7 days:
```
Automatic equal split among all PRs
@you: $50 (50%)
@other: $50 (50%)
```

### Connecting Your Wallet

**When to connect:** Before or after PR merge (payment waits for you)

**How:**
1. Visit ubounty.ai/settings
2. Login with GitHub
3. Click "Connect Wallet"
4. Approve connection in wallet

**Payment executes automatically** once wallet is connected.

### If Payment Pending

**Check:**
1. Do you have wallet connected?
2. Is it on Base network?
3. Did creator make decision yet?

**Still waiting?** Creator has up to 7 days, then auto-split executes.

---

## Maximizing Earnings

### Choose Wisely

**Focus on:**
- Technologies you know well (faster work)
- Fair pay for effort (calculate hourly rate)
- Clear requirements (less risk)

**Calculate hourly rate:**
```
$100 bounty ÷ 4 hours estimated = $25/hour ✓
$50 bounty ÷ 10 hours estimated = $5/hour ✗
```

### Build Reputation

**Quality work leads to:**
- Creator tags you for future bounties
- Trust and repeat opportunities
- Higher-paying work

### Submit Quality Work

**Don't rush to be first** - quality beats speed

**Include:**
- Complete solution
- Tests
- Documentation
- Clean code

### Work Strategically

**One bounty at a time** unless you're experienced

**Multiple PRs on same bounty:**
- Submit core fix
- Add comprehensive tests
- Improve documentation
= Higher payment allocation

---

## Common Scenarios

### Someone Submitted First

**You can still submit!**

Multiple contributors are allowed. Submit if:
- Your solution is different/better
- You can add complementary work (tests, docs)

Quality matters more than timing.

### Maintainer Won't Merge

**Possible reasons:**
- Code quality issues
- Doesn't fully solve issue
- Breaking changes

**Action:**
- Read feedback carefully
- Make requested changes
- Be patient and professional

### Got 0% Payment

**Why:**
- Creator determined work didn't solve issue
- Quality issues
- Another developer did core work
- Your contribution was minor

**Learn for next time:**
- Clarify requirements upfront
- Focus on core issue
- Communicate during development

### Payment Wrong Amount

**Check:**
- GitHub comment for allocation breakdown
- Calculate: Bounty × Your % = Your Payment
- Multiple PRs may be combined

**Still wrong?** Contact support immediately

---

## Troubleshooting

### PR Not Linked to Bounty

**Problem:** PR merged but system doesn't recognize it

**Cause:** Missing "Fixes #123" in PR description

**Fix:** Edit PR description to add reference (works even after merge)

### Can't Connect Wallet

**Try:**
- Wallet unlocked?
- On Base network?
- Pop-up blocker disabled?
- Try different browser

### Payment Not Received

**Check:**
1. Wallet connected in settings?
2. Correct wallet address?
3. Switch to Base network in wallet
4. Wait 5-10 minutes

**Still missing?** Check transaction hash on BaseScan or contact support

---

## Pro Tips

**Before starting:**
- Read entire issue and comments
- Check if anyone else is working on it
- Verify bounty is still active
- Calculate if hourly rate is acceptable

**While working:**
- Comment that you're working on it
- Ask questions early
- Test thoroughly
- Follow repo conventions

**When submitting:**
- Include "Fixes #123" in description
- Clear explanation of changes
- Screenshots if relevant
- Ensure all tests pass

**After submitting:**
- Connect wallet before payment decision
- Monitor PR for feedback
- Respond promptly
- Be professional

---

## Resources

### Documentation

- [Getting Started](./Getting_Started.md) - Platform overview
- [Payout Logic](./Payout_logic.md) - How payments work
- [Payment & Security](./Payment_Security.md) - Fund safety
- [Platform Features](./Platform_Features.md) - All features
- [FAQ](./FAQ.md) - Common questions

### Support

- Docs: This repository

---

## Quick Reference

| Item | Detail |
|------|--------|
| Payment Currency | USDC on Base |
| Payment Speed | 3-5 seconds after approval |
| Decision Window | Up to 7 days |
| Auto-Split | After 7 days if no decision |
| Platform Fee | $0 for developers |
| Minimum Bounty | $10 USDC |

---

**Ready to start earning?**

Browse bounties at [ubounty.ai/bounties](https://ubounty.ai/bounties)

---

