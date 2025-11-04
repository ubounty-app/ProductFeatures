# Frequently Asked Questions

## General

**What is Ubounty.ai?**

Automated cryptocurrency bounty platform for GitHub issues. Creators fund bounties, developers earn USDC by solving them.

**What makes Ubounty different?**

- Instant crypto payments (3-5 seconds)
- Multiple contributors can earn
- Fully automated
- 7-day auto-split protection
- Transparent blockchain transactions

**Who can use it?**

Anyone 18+ with GitHub account and crypto wallet. Not available in restricted jurisdictions.

**Is it free?**

- Developers: Free (no fees)
- Creators: 5% platform fee

**What currency?**

USDC only (stablecoin, 1 USDC = $1 USD)

**What blockchain?**

Base network (Coinbase's Layer 2)

---

## For Creators

**How do I create a bounty?**

1. Login with GitHub
2. Paste issue URL
3. Set amount
4. Fund with USDC
5. Done in 10-20 seconds

**Minimum bounty?**

$10 USDC

**Can I cancel?**

Before PRs merged: Contact support
After PRs merged: No, must allocate payment

**Can I change amount after funding?**

No, amount is locked

**What if no one works on it?**

- Increase amount
- Clarify requirements
- Share in communities
- Extend deadline

**How long do I have to decide payment?**

7 days from first PR merge. After that, auto-split executes.

**Can I change my decision?**

No, decisions are final

**What if maintainer merges bad PR?**

You control payment - can allocate 0%

---

## For Developers

**Do I claim bounties first?**

No claiming system. Anyone can work on any bounty.

**How do I get paid?**

1. Submit PR with "Fixes #123"
2. Maintainer merges
3. Creator allocates %
4. USDC arrives in wallet (3-5 seconds)

**Do I need crypto to start?**

No - you're receiving payment, not sending

**What if someone submits first?**

You can still submit. Multiple contributors allowed.

**How long until payment?**

2-7 days (up to 7-day decision window)

**What if I get 0%?**

Creator determined work didn't adequately solve issue. Learn for next time.

**Can I cash out USDC?**

Yes - transfer to exchange (Coinbase, Kraken, etc.) and sell for USD

---

## Payments & Fees

**What are the fees?**

Creators: 5% platform fee
Developers: $0

**Who pays gas fees?**

Platform covers them (~$0.01 per transaction)

**Can I get a refund?**

Before PRs merged: Contact support
After PRs merged: No

**How do taxes work?**

Consult tax advisor. Export transaction history from dashboard for records.

---

## Security

**Is my money safe?**

Yes - locked in blockchain smart contract, not company custody

**What if Ubounty shuts down?**

Funds remain on blockchain, accessible via smart contract

**Can Ubounty steal funds?**

No - we never have access to escrow funds or your private keys

**What if I lose my wallet?**

We cannot help. Keep recovery phrase secure.

**How do I avoid scams?**

- Never share recovery phrase
- Verify URLs (ubounty.ai only)
- Real support never asks for keys
- No DM support

---

## Technical

**What wallets work?**

MetaMask, Coinbase Wallet, Rainbow, WalletConnect-compatible wallets

**Can I use exchange wallet?**

Not recommended. Use non-custodial wallet (MetaMask, Coinbase Wallet, etc.)

**Transaction failed?**

- Check USDC balance
- Switch to Base network
- Unlock wallet
- Retry

**Payment not received?**

- Wallet connected?
- On Base network?
- Creator decided yet? (up to 7 days)
- Check BaseScan with transaction hash

**Can I update wallet address?**

Yes in settings. Future payments use new address. Already-approved payments go to old address.

**Why Base network?**

Low fees ($0.01 vs $5-50 on Ethereum) and fast (3-5 seconds)

---

## Troubleshooting

**Bounty not on GitHub**

Wait 30-60 seconds. Check permissions. Contact support if still missing.

**PR not linked**

Add "Fixes #123" to PR description (works even after merge)

**Can't connect wallet**

- Wallet unlocked?
- Base network selected?
- Pop-up blocker disabled?
- Try different browser

**Wrong payment amount**

Check GitHub comment for breakdown. Calculate: Bounty × Your % = Payment

---

## More Information

**Detailed Guides:**

- [Getting Started](./Getting_Started.md) - Quick start
- [Bounty Creator Guide](./Bounty_Creator_Guide.md) - Creating bounties
- [Developer Guide](./Developer_Guide.md) - Earning bounties
- [Payment & Security](./Payment_Security.md) - Security details
- [Platform Features](./Platform_Features.md) - All features
- [Payout Logic](./Payout_logic.md) - Payment workflows

**Support:**


**Response Time:** 24 hours (security issues prioritized)

---

