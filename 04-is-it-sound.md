# Gate 4: Is the Engineering Sound?

**Core question:** Is your technical approach correct, or are you cargo-culting?

## Checklist

- [ ] You can explain your architecture to someone in 2 minutes on a whiteboard
- [ ] You've chosen technologies you actually know (or have time to learn properly)
- [ ] You're not using a framework/tool just because it's trendy
- [ ] Your data model makes sense for the actual queries you'll run
- [ ] You have a deployment strategy that isn't "figure it out later"

## Critical Questions

### Architecture
1. **Can you draw the system in 3 boxes or fewer?** If not, it's too complex for the problem.
2. **Are you using microservices for something that's obviously a monolith?** A side project does not need Kubernetes.
3. **Is your tech stack justified?** React + Node + Postgres + Redis + Docker + K8s for a CRUD app is engineering cosplay.
4. **What happens when a component fails?** If you don't know, you haven't designed a system — you've assembled parts.

### Frontend Specific
1. **Does this need to be an SPA?** Server-rendered HTML with a sprinkle of JS solves 80% of web apps.
2. **Are you pulling in 200MB of node_modules for a todo app?**
3. **Does the UI actually need to be "reactive"?** Many apps work fine with form submissions and page reloads.

### Backend Specific
1. **SQLite or Postgres?** If you said "Postgres for a single-user app," doubt yourself.
2. **Do you actually need an ORM?** Raw SQL with parameterized queries is fine and often clearer.
3. **Is your API design consistent?** REST, GraphQL, or RPC — pick one, not a Frankenstein mix.

### Engineering Best Practices
- [ ] Secrets are in environment variables, NOT in code
- [ ] `.env` is in `.gitignore`
- [ ] Dependencies are pinned (not floating `latest`)
- [ ] There's at least a plan for testing (not "I'll add tests later" which means never)
- [ ] Error handling exists beyond `catch(e) { console.log(e) }`

## The Resume-Driven Development Trap

Are you choosing this stack because:
- It solves the problem well? → Good
- You want to learn it? → Honest, but say so
- It looks impressive on your resume? → You'll build a worse product
- Everyone on Twitter uses it? → That's not a reason

## Scoring

| Score | Criteria |
|-------|----------|
| PASS | Architecture is simple, justified, and you understand every piece |
| CONDITIONAL | Some tech choices are aspirational — you'll need learning time |
| FAIL | Over-engineered, cargo-culted, or you can't explain why you chose the stack |

## Notes

_Write your findings here_
