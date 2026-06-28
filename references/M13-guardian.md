# MODULE 13 — Guardian Monitoring Protocol

## Purpose
Post-investment surveillance system. Guardian monitors active positions and issues early exit signals BEFORE a project collapses.

## Monitoring Cadence

### Daily (automated alerts if possible)
- Large outflows from project treasury wallet (>5% of TVL)
- Smart contract: new functions deployed or proxy upgraded
- Token price: sudden >20% drop without market-wide cause
- Withdrawal queue: backlog forming?

### Weekly (manual check)
- Team wallet activity: are insiders selling?
- Social media: founder posting frequency (silence = yellow flag)
- Community: admin/moderator activity (departures = red flag)
- Website: any claims quietly removed? (use Wayback Machine)
- Partnership page: any logos disappeared?

### Monthly (full mini-audit)
- Re-run M6 (smart contract): any changes since initial audit?
- Re-run M3 (community): engagement trend up or down?
- Check regulatory news: any new warnings issued?
- Token holder distribution: more concentrated or distributed?

## Exit Signal Hierarchy

### 🔴 EXIT IMMEDIATELY (same day)
- Team wallet(s) selling >10% of holdings
- Contract ownership transferred to unknown wallet
- Withdrawal function disabled or delayed >72 hours
- Regulatory enforcement action announced
- Mixer/tumbler activity from project wallet
- Team members deleting social accounts

### 🟠 PREPARE TO EXIT (within 1 week)
- CEO/founder goes silent >2 weeks
- Multiple core team members announce departure
- Liquidity pool showing large removal transactions
- "Technical upgrade" requiring re-staking of funds
- Unusual transaction patterns from treasury

### 🟡 INCREASE MONITORING (watch closely)
- Community admin turnover
- Promised roadmap milestone missed without explanation
- New competitor claims project is a fork/copy
- Exchange delisting rumors
- FUD (even if seemingly coordinated — verify the underlying facts)

## Guardian Report Template

```
GUARDIAN ALERT — [Project Name]
Date: [Date]
Alert Level: 🔴/🟠/🟡

TRIGGER EVENT:
[What was observed]

DATA POINTS:
- [Specific transaction/event with links]
- [Additional evidence]

RECOMMENDED ACTION:
[Exit / Reduce position / Monitor closely]

NEXT CHECK: [Date]
```

## Monitoring Stack (free tools)
- **Etherscan alerts** — wallet activity notifications
- **DeBank** — portfolio + wallet tracking
- **Arkham Intelligence** — entity labeling, fund flows
- **Telegram** — set keyword alerts in community channels
- **Google Alerts** — project name + "scam" / "hack" / "rug"
- **DeFiLlama** — TVL monitoring for DeFi protocols
