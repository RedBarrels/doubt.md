# Gate 7: Does It Have to Be Done This Way?

**Core question:** Is your chosen approach the right one, or just the first one you thought of?

## Checklist

- [ ] You've considered at least 3 alternative approaches
- [ ] You can articulate WHY this approach over the alternatives
- [ ] You've identified what you'd lose by choosing a different approach
- [ ] The approach matches the problem's actual constraints (not imagined ones)
- [ ] You're not locked into a path just because you already started

## The Alternatives Matrix

| Approach | Pros | Cons | Effort | Risk |
|----------|------|------|--------|------|
| Your current approach | | | | |
| Alternative 1: | | | | |
| Alternative 2: | | | | |
| Do nothing | | | | |

**"Do nothing" must always be an option.** If doing nothing is viable, your project needs to justify its existence against inaction.

## Critical Questions

### Could this be simpler?
1. **Does this need an app, or would a spreadsheet work?** Seriously.
2. **Does this need a backend, or could it be client-side only?**
3. **Does this need AI, or would a regex/rule-based approach work?** Not everything needs an LLM.
4. **Does this need real-time, or is a cron job + static page fine?**
5. **Does this need a custom solution, or does a SaaS product cover 90% of it?**

### Could this be done differently?
1. **Are you building a platform when you need a script?**
2. **Are you building an API when a CLI would do?**
3. **Are you building a dashboard when an email report would do?**
4. **Are you automating something that happens once a month?** Manual might be fine.
5. **Are you building for scale you'll never reach?**

### Are your constraints real?
1. **"It needs to be fast"** — How fast? Have you measured the current speed? Is it actually slow?
2. **"It needs to handle millions of requests"** — Will it ever? Really?
3. **"It needs to be cross-platform"** — Who uses it on platforms other than yours?
4. **"It needs to be offline-capable"** — When was the last time you were offline?
5. **"It needs a mobile app"** — Or does a responsive website work?

## The Sunk Cost Trap

If you've already started and this gate makes you doubt:
- **Code you've written is not a reason to continue.** That's sunk cost.
- **Time you've spent is not an investment to protect.** It's gone.
- **Switching costs are real but often smaller than the cost of continuing wrong.**

The best time to pivot was yesterday. The second best time is now.

## Scoring

| Score | Criteria |
|-------|----------|
| PASS | This approach is the simplest viable path, with alternatives considered and rejected for clear reasons |
| CONDITIONAL | Better approaches might exist — research needed before committing |
| FAIL | You chose the first/coolest approach without considering alternatives, or a clearly simpler option exists |

## Notes

_Write your findings here_
