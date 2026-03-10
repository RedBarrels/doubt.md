# Gate 6: Is the Cost Right?

**Core question:** Are you burning money, tokens, and time proportional to the value you're creating?

## Checklist

- [ ] You know the actual cost of your AI/API usage (not a guess)
- [ ] You've compared the cost of building vs buying/using an existing solution
- [ ] You have a budget cap and will stop if you hit it
- [ ] You've calculated cost per user/request at scale (not just for demos)
- [ ] Rate limits are in place (both API-side and your own)

## AI/LLM Token Economics

| Metric | Value |
|--------|-------|
| Model used | |
| Cost per 1K input tokens | |
| Cost per 1K output tokens | |
| Average tokens per request | |
| Estimated requests per day | |
| **Daily cost** | |
| **Monthly cost** | |
| Budget cap | |

### Critical Questions — Token Spending
1. **Are you using Opus when Haiku would do?** Most classification, extraction, and routing tasks don't need the biggest model.
2. **Are you sending the entire codebase as context when you need 3 lines?** Context window abuse is the #1 token waste.
3. **Do you have caching?** Identical prompts should not cost you twice.
4. **Are you in a retry loop burning tokens?** Failed requests that retry 5 times cost 5x.
5. **Is your system prompt enormous?** Every request pays for that system prompt again.

### Real Example — Your Projects

From your Claude Code usage:
- **AI-Inventory**: $37.59 in a single session. 47M cache read tokens. That's aggressive.
- **Hecate**: $14.46 per session.
- **Yuna avatar**: $3.29 for asset generation.

Ask yourself: did the output justify the cost? Would a cheaper model have produced 90% of the result at 10% of the cost?

## Time Cost

Time is the cost people always ignore:
1. **How many hours will this take to build?** Be honest. Multiply your estimate by 3.
2. **What else could you do with that time?** Opportunity cost is real.
3. **Is "learning" the actual goal?** That's valid — but budget for it honestly.

## Infrastructure Cost

- [ ] Can this run on a free tier? (Vercel, Fly.io, Railway free plans)
- [ ] Do you actually need a database server or would SQLite + file storage work?
- [ ] Are you paying for services you don't need yet? (monitoring, CDN, managed DB)
- [ ] What's the monthly cost at 0 users? If it's > $0 with no users, question everything.

## Scoring

| Score | Criteria |
|-------|----------|
| PASS | Costs are known, budgeted, proportional to value, and rate-limited |
| CONDITIONAL | Costs are estimated but not measured — needs monitoring before scaling |
| FAIL | No idea what you're spending, no budget, or cost exceeds any plausible value |

## Notes

_Write your findings here_
