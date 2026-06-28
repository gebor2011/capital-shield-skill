# MODULE 6 — Smart Contract Deep Analysis

## Priority: Run automated tools FIRST, then interpret results

### Phase 1 — Automated Scanning (always do first)

**Input needed:** Contract address + chain (ETH/BSC/Polygon/SOL/etc.)

**Tools to check (in order):**
1. **GoPlus Security** — `https://api.gopluslabs.io/api/v1/token_security/{chain_id}?contract_addresses={address}`
2. **TokenSniffer** — `https://tokensniffer.com/token/{chain}/{address}`
3. **De.Fi Scanner** — `https://de.fi/scanner`
4. **Etherscan/BscScan** — check if contract is verified (source code visible)

### Phase 2 — Manual Contract Review Checklist

```solidity
// RED FLAG FUNCTIONS — if any present, score M6 = 0 pts

// 1. MINT — can team create unlimited tokens?
function mint(address to, uint256 amount) public onlyOwner

// 2. BLACKLIST — can team freeze wallets?
function blacklist(address account) public onlyOwner
function setBlacklist(address _address, bool _isBlacklisting)

// 3. FEE MANIPULATION — can team set 100% tax?
function setTaxFee(uint256 taxFee) external onlyOwner
// Check: is there a maximum fee cap? (legitimate projects cap at 10–25%)

// 4. TRANSFER PAUSE — can team halt all transfers?
function pause() public onlyOwner

// 5. MAX WALLET REMOVAL — can team lift anti-whale limits?
function setMaxWalletSize(uint256 maxWalletSize)
```

### Phase 3 — Ownership & Liquidity

```
□ contract.owner() → is it 0x000...000 (renounced) or team wallet?
□ If not renounced: owner can call any onlyOwner function at any time
□ Liquidity pool: is LP locked? (check Unicrypt, PinkSale, Team.Finance)
□ LP lock duration: 6 months minimum, 1 year preferred
□ LP token holder: who holds the LP tokens if not locked?
```

### Phase 4 — Token Distribution Analysis

```
Using Etherscan Token Holders:
□ Top 10 wallets: what % of total supply?
  → >50% in top 10 = extreme centralization risk
  → >30% in top 10 = high risk
  → <20% in top 10 = acceptable
□ Team/dev wallet(s): identifiable? What % do they hold?
□ Vesting contract: are team tokens time-locked?
□ Dead wallet (0x000...dEaD): burned tokens confirmed?
```

### Phase 5 — Honeypot Test

```
Simulate buy AND sell transaction before investing:
1. Use honeypot.is for EVM chains
2. Buy small test amount ($5–10)
3. Attempt to sell 100% immediately
4. If sell fails or tax >30% → HONEYPOT → M6 = 0 pts
```

### Phase 6 — Historical Transaction Analysis

```
□ Deployer wallet: what else has it deployed?
   → Same deployer = same team, check other projects' outcomes
□ Pre-sale wallets: still holding or already sold?
□ Large buys before launch announcement: insider trading?
□ Sell pressure from team/insiders post-launch?
```

### Integration with External Skill

If source code is available (GitHub repository):
→ Apply cloudflare/security-audit-skill for deep code vulnerability analysis
→ Focus: reentrancy, integer overflow, access control, flash loan attack vectors
→ Results feed back into M6 score

### Scoring
- All checks pass, contract renounced, liquidity locked 1yr+: 10–12 pts
- Minor issues (high fees but capped, owner not renounced but clean): 6–9 pts
- Unverified contract but no honeypot: 3–5 pts
- Blacklist OR mint OR pause function active: 1–3 pts
- Honeypot confirmed: 0 pts + CRITICAL FINDING + AVOID verdict
- Mixer interaction from deployer: 0 pts + CRITICAL FINDING
