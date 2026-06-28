# MODULE 12 — AML / Financial Crime Risk Assessment

## Objective
Determine if the project poses money laundering risks — either as a target of regulators or as an instrument enabling financial crime.

## AML Red Flag Checklist

### Structural Red Flags
```
□ No KYC for transactions above regulatory thresholds
□ Anonymous wallets explicitly promoted as feature
□ Integration with known mixers (Tornado Cash, etc.)
□ No AML policy published (required in most jurisdictions)
□ Incorporated in FATF high-risk or non-cooperative jurisdiction
□ No transaction limits or monitoring
```

### Watchlist Screening
Check project AND key wallets against:
- **OFAC SDN List** — sanctioned individuals/entities (US Treasury)
- **EU Consolidated Sanctions List**
- **UN Security Council Sanctions**
- **FinCEN Advisories** (US)
- **FATF Grey/Black List jurisdictions**
- **Chainalysis / Elliptic** — wallet risk scoring

### On-Chain AML Signals
```
□ Deployer wallet received funds from sanctioned address?
□ Project wallet interacted with Tornado Cash post-2022?
□ Large transactions from high-risk jurisdiction clusters?
□ Structuring behavior (many small transactions just below reporting thresholds)?
□ Rapid cycling: funds in → immediately out → different wallet?
```

### Legal Recourse Test
*If the project disappears tomorrow:*
- Is there a named legal entity to sue?
- In what jurisdiction?
- Are customer funds legally segregated?
- Is there investor protection (like EU's MiCA framework)?

**If all answers are NO → maximum AML risk score**

## Jurisdiction Risk Tier

| Tier | Jurisdictions | Risk |
|------|--------------|------|
| High-risk | Marshall Islands, Seychelles, Vanuatu, Panama (crypto-only ops) | 🔴 |
| Medium-risk | UAE, Singapore (unregulated), BVI | 🟡 |
| Low-risk | EU (MiCA compliant), UK (FCA registered), US (SEC/CFTC registered) | 🟢 |

## Scoring
- Full KYC/AML, licensed, clean wallet history: 4–5 pts
- Offshore but clean wallets, no watchlist hits: 2–3 pts
- No KYC, offshore, no watchlist hits: 1–2 pts
- Watchlist interaction or mixer usage: 0 pts + CRITICAL FINDING
