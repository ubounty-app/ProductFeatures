# Payment & Security

## Overview

How Ubounty protects your funds and executes payments securely using blockchain technology.

---

## Table of Contents

1. [Payment System](#payment-system)
2. [Escrow & Security](#escrow--security)
3. [Transaction Transparency](#transaction-transparency)
4. [Platform Security](#platform-security)
5. [User Responsibilities](#user-responsibilities)

---

## Payment System

### Currency: USDC

**What:** USD Coin stablecoin where 1 USDC = 1 USD

**Why USDC:**
- Stable value (no volatility)
- Fast transfers (seconds)
- Low fees (~$0.01)
- Global compatibility

### Network: Base

**What:** Coinbase's Layer 2 blockchain

**Why Base:**
- Low fees ($0.01 vs $5-50 on Ethereum)
- Fast (3-5 second confirmations)
- Secure (backed by Ethereum)
- Coinbase integration

### Payment Protocol: x402

Enables:
- Instant payment verification
- Direct escrow deposits
- Automatic execution
- Cryptographic proof

---

## Escrow & Security

### How Escrow Works

When you fund a bounty:

```
Your Wallet → Smart Contract → Developer Wallet
   (You pay)    (Escrow holds)    (Gets paid)
```

**Funds are locked until:**
- PR is merged
- Creator makes payment decision
- Developer has wallet connected

### Security Features

**1. Blockchain Escrow**

✓ Funds locked on-chain (not on company servers)
✓ Platform cannot access funds
✓ Smart contract enforces rules
✓ Publicly verifiable

**2. Automatic Verification**

System verifies:
- Correct sender address
- Correct amount
- Blockchain confirmation
- Transaction valid

**3. Payment Execution**

When payment decision made:
- Smart contract releases funds
- Transfer to developer wallet
- 3-5 second execution
- Irreversible

### What If Ubounty Shuts Down?

**Your funds are safe** because:
- Funds are on blockchain, not company servers
- Smart contracts operate independently
- You can interact with contracts directly if needed

---

## Transaction Transparency

### Public Blockchain

**Everything is visible:**
- Wallet addresses involved
- Amounts transferred
- Timestamps
- Transaction status

**Cannot see:**
- Your name
- Your email
- Personal information

### Verifying Transactions

**Using BaseScan:**

1. Get transaction hash (from GitHub comment or bounty page)
2. Visit basescan.org
3. Paste hash in search
4. View full transaction details

**What you'll see:**
```
Transaction Hash: 0xabc123...
Status: Success ✓
From: 0x742d35Cc... (Your Wallet)
To: 0x9B8f46... (Escrow)
Value: 105 USDC
Gas Fee: $0.01
```

---

## Platform Security

### Authentication

**GitHub OAuth:**
- No password storage on our side
- 2FA support (if enabled on GitHub)
- Standard OAuth 2.0

**We access:**
- Username and email
- Permission to comment on issues

**We don't access:**
- Your code
- Private repositories (unless specifically authorized)
- Your GitHub password

### Data Protection

**What we store:**
- GitHub username
- Wallet addresses (public info)
- Bounty metadata
- Transaction hashes (public blockchain data)

**What we DON'T store:**
- Private keys
- Recovery phrases
- Passwords

**Security measures:**
- Encrypted at rest
- Encrypted in transit (HTTPS)
- Regular security audits

### We Never Ask For

❌ Private keys
❌ Recovery phrases
❌ Wallet passwords
❌ Seed phrases

**If someone asks for these claiming to be Ubounty support, it's a scam.**

---

## User Responsibilities

### Your Wallet Security

**Critical: You control your keys**

Ubounty NEVER has access to:
- Your private keys
- Your recovery phrase
- Ability to move your funds

**If you lose your recovery phrase:**
- Funds are permanently inaccessible
- No "forgot password" recovery
- Ubounty cannot help

### Recovery Phrase Security

**Do:**
- Write on paper
- Store in safe/lockbox
- Keep multiple copies in different locations

**Don't:**
- Save digitally
- Store in cloud
- Take screenshots
- Share with anyone

### Transaction Safety

**Before approving transactions:**
- Verify recipient address
- Check amount is correct
- Understand it's irreversible

**Once sent, cannot be reversed.**

### Common Scams

**Phishing:**
- Fake websites (check URL carefully)
- Emails asking for keys
- DMs claiming to be support

**Red flags:**
- Asking for recovery phrase
- Asking for private key
- Urgency tactics
- Contact via DM

**Real support:**
- Never asks for keys
- Uses official channels only
- No urgency pressure

---

## Risk Mitigation

### Smart Contract Security

- Using audited, standard contracts
- Code is public and verifiable
- Emergency pause mechanism

### Transaction Verification

Multiple checks:
- Amount matches
- Addresses correct
- Blockchain confirmed
- Sufficient balance

### Payment Safety

**For creators:**
- Funds locked until decision
- Cannot be stolen or lost
- Verifiable on blockchain

**For developers:**
- Payment guaranteed after approval
- No chargebacks
- Automatic execution

---

## Best Practices

### For Creators

**Before funding:**
- Double-check amount
- Verify GitHub issue URL
- Ensure sufficient USDC

**Wallet:**
- Use reputable wallet
- Test with small amount first
- Keep recovery phrase secure

### For Developers

**Wallet setup:**
- Connect early (don't wait)
- Verify address is correct
- Use Base network

**Receiving payment:**
- Check wallet on Base network
- Verify transaction on BaseScan
- Report issues immediately

### For Everyone

**Security:**
- Never share recovery phrases
- Verify URLs before connecting wallet
- Be skeptical of unsolicited messages
- Use 2FA on GitHub

**Transactions:**
- Always verify addresses
- Understand irreversibility
- Start with small amounts
- Use blockchain explorer to verify

---

## Summary

**Ubounty's Security Model:**

1. **Blockchain Escrow** - Funds on-chain, not company custody
2. **Transparent** - All transactions publicly verifiable
3. **Automated** - Smart contracts enforce rules
4. **User-Controlled** - You control your keys
5. **Auditable** - Complete transaction history

**Your Responsibilities:**

- Secure your wallet and recovery phrase
- Verify transaction details
- Report suspicious activity
- Follow best practices

**Platform Commitments:**

- Never ask for private keys
- Transparent fee structure
- Regular security audits
- Responsive security support

---

## Questions or Concerns?



---

## Additional Resources

- [Getting Started](./Getting_Started.md) - Platform overview
- [Payout Logic](./Payout_logic.md) - How payments work
- [Bounty Creator Guide](./Bounty_Creator_Guide.md) - Creating bounties
- [Developer Guide](./Developer_Guide.md) - Earning bounties
- [FAQ](./FAQ.md) - Common questions

---

