# The 7 Gates

## Gate 1: Does It Already Exist?

**Core question:** Am I reinventing the wheel?

### Checklist

- [ ] Searched GitHub for similar projects (keywords, tags)
- [ ] Searched product directories (Product Hunt, AlternativeTo, G2)
- [ ] Searched academic papers / arXiv if it's a novel algorithm
- [ ] Asked in relevant communities (Reddit, Discord, HN)
- [ ] Checked if a library/package already does this (npm, PyPI, crates.io)

### Critical Questions

**If something similar exists:**
1. What exactly does the existing solution lack? Be specific — "it's not good enough" is not an answer.
2. Is the gap you identified real or imagined? Have other users complained about it?
3. Could you contribute to the existing project instead? A PR is cheaper than a new repo.
4. Is the existing solution abandoned? If active, you'll be competing with momentum.

**If nothing exists:**
1. Why not? Possible answers:
   - Nobody thought of it → unlikely, be skeptical
   - It's too niche → fine, but who's your user?
   - It was tried and failed → find out WHY it failed
   - The problem doesn't actually exist → you might be solving a phantom
2. Are you searching with the right terms? Your idea might exist under a name you haven't considered.

### Scoring

| Score | Criteria |
|-------|----------|
| PASS | Nothing comparable exists, or existing solutions have well-documented, verified gaps |
| CONDITIONAL | Similar things exist but with clear, articulable differences |
| FAIL | This already exists and works fine. You're building a bicycle. |

---

## Gate 2: Is It Needed?

**Core question:** Does anyone actually need this, or are you scratching your own itch and calling it a product?

### Checklist

- [ ] Can you name 3 specific people (not yourself) who would use this?
- [ ] Have you talked to potential users (not friends/family who'll say yes to anything)?
- [ ] Is there evidence of demand? (forum posts asking for this, complaints about current solutions)
- [ ] Can you describe the user's current workflow WITHOUT your tool?
- [ ] Would the user's life meaningfully change without this?

### Critical Questions

1. **Who is the user?** "Everyone" is not an answer. "Developers" is barely better. Be painfully specific.
2. **What pain are they feeling RIGHT NOW?** If you have to explain the pain to them, it's not real pain.
3. **How are they solving this today?** If they're not solving it at all, maybe it's not a problem.
4. **What's the user's alternative if you never build this?** If the answer is "they'll be fine," you have your answer.
5. **Is this a vitamin or a painkiller?** Vitamins are nice-to-have. Painkillers get bought.
6. **Are you building this because you CAN or because you SHOULD?** Having the skills to build something is not a reason to build it.

### The Portfolio Trap

Be honest: is this a resume/portfolio piece? That's a valid reason — but call it what it is. Don't pretend a portfolio project is a product. Portfolio projects have different success criteria (demonstrates skill) vs products (solves a problem).

### Scoring

| Score | Criteria |
|-------|----------|
| PASS | Clear evidence of need from people who aren't you |
| CONDITIONAL | You need it personally and suspect others might too — but haven't verified |
| FAIL | You can't name a single person who asked for this |

---

## Gate 3: Is It Effective?

**Core question:** Will this actually solve the problem, or just look like it does?

### Checklist

- [ ] Can you describe the measurable outcome? (not "makes life easier" — HOW MUCH easier?)
- [ ] Have you defined what "done" looks like?
- [ ] Have you identified how you'll know it's working vs not working?
- [ ] Is there a simpler solution that achieves 80% of the result with 20% of the effort?

### Critical Questions

1. **What's the success metric?** "Users like it" is not a metric. "Reduces X from 30 min to 5 min" is.
2. **Does this solve the root cause or just a symptom?** Building a dashboard for bad data doesn't fix the data.
3. **What's the minimum viable version?** If you can't ship something useful in a weekend, scope is wrong.
4. **Are you optimizing for the right thing?** Speed doesn't matter if accuracy is the problem.
5. **Have you considered second-order effects?** Your solution might create new problems.

### The Demo Trap

Does this only work in demos? Many projects look great in controlled conditions but fall apart with:
- Real-world data (messy, incomplete, contradictory)
- Scale (works for 10 items, dies at 10,000)
- Edge cases (the 20% of scenarios that take 80% of the effort)
- Users who don't read instructions

### The Complexity Trap

If your effectiveness depends on users configuring 15 settings correctly, a specific environment/setup, reading documentation before first use, or "using it the right way" — then it's not effective. Effective tools work despite users, not because of compliant users.

### Scoring

| Score | Criteria |
|-------|----------|
| PASS | Clear metric, achievable scope, proven approach |
| CONDITIONAL | Promising but unvalidated — needs a prototype/proof-of-concept first |
| FAIL | No measurable outcome, or the approach fundamentally can't deliver |

---

## Gate 4: Is the Engineering Sound?

**Core question:** Is your technical approach correct, or are you cargo-culting?

### Checklist

- [ ] You can explain your architecture to someone in 2 minutes on a whiteboard
- [ ] You've chosen technologies you actually know (or have time to learn properly)
- [ ] You're not using a framework/tool just because it's trendy
- [ ] Your data model makes sense for the actual queries you'll run
- [ ] You have a deployment strategy that isn't "figure it out later"

### Critical Questions

**Architecture:**
1. Can you draw the system in 3 boxes or fewer? If not, it's too complex for the problem.
2. Are you using microservices for something that's obviously a monolith? A side project does not need Kubernetes.
3. Is your tech stack justified? React + Node + Postgres + Redis + Docker + K8s for a CRUD app is engineering cosplay.
4. What happens when a component fails? If you don't know, you haven't designed a system — you've assembled parts.

**Frontend Specific:**
1. Does this need to be an SPA? Server-rendered HTML with a sprinkle of JS solves 80% of web apps.
2. Are you pulling in 200MB of node_modules for a todo app?
3. Does the UI actually need to be "reactive"? Many apps work fine with form submissions and page reloads.

**Backend Specific:**
1. SQLite or Postgres? If you said "Postgres for a single-user app," doubt yourself.
2. Do you actually need an ORM? Raw SQL with parameterized queries is fine and often clearer.
3. Is your API design consistent? REST, GraphQL, or RPC — pick one, not a Frankenstein mix.

### Engineering Best Practices

- [ ] Secrets are in environment variables, NOT in code
- [ ] `.env` is in `.gitignore`
- [ ] Dependencies are pinned (not floating `latest`)
- [ ] There's at least a plan for testing (not "I'll add tests later" which means never)
- [ ] Error handling exists beyond `catch(e) { console.log(e) }`

### The Resume-Driven Development Trap

Are you choosing this stack because it solves the problem well (good), you want to learn it (honest, but say so), it looks impressive on your resume (you'll build a worse product), or everyone on Twitter uses it (not a reason)?

### Scoring

| Score | Criteria |
|-------|----------|
| PASS | Architecture is simple, justified, and you understand every piece |
| CONDITIONAL | Some tech choices are aspirational — you'll need learning time |
| FAIL | Over-engineered, cargo-culted, or you can't explain why you chose the stack |

---

## Gate 5: Is It Secure?

**Core question:** Will this get hacked in minutes by a bored teenager?

### Checklist — The Absolute Minimum

- [ ] No secrets in source code (API keys, passwords, tokens)
- [ ] `.env` file exists AND is in `.gitignore`
- [ ] No secrets in git history (if they were ever committed, they're compromised — rotate them)
- [ ] HTTPS everywhere (no HTTP, no "it's just local")
- [ ] Dependencies are from trusted sources and not wildly outdated
- [ ] Input is validated/sanitized on the SERVER, not just the client

### OWASP Top 10 Quick Scan

| Vulnerability | Status | Notes |
|--------------|--------|-------|
| Injection (SQL, NoSQL, OS command) | | |
| Broken Authentication | | |
| Sensitive Data Exposure | | |
| XML External Entities (XXE) | | |
| Broken Access Control | | |
| Security Misconfiguration | | |
| Cross-Site Scripting (XSS) | | |
| Insecure Deserialization | | |
| Using Components with Known Vulnerabilities | | |
| Insufficient Logging & Monitoring | | |

### Critical Questions

1. **What's the blast radius if you get hacked?** User data leaked? Financial loss? Just your embarrassment?
2. **Are you storing user passwords?** If yes, are you using bcrypt/argon2? If you're rolling your own crypto, stop.
3. **Are you handling user data?** GDPR/privacy implications? Do you even need to store it?
4. **Can someone enumerate your users/data through your API?** Try incrementing IDs.
5. **What happens if someone sends 10,000 requests per second?** Rate limiting?
6. **Are your Docker images based on `latest`?** Pin your base images.
7. **Is your `.git` folder exposed on your web server?** Check.
8. **Are you running as root?** Don't.

### The "It's Just a Side Project" Trap

"Nobody will hack my side project" is what everyone says until their AWS bill hits $50,000 from crypto mining, their API keys get scraped from a public repo, or their users' data ends up on a pastebin. If it's on the internet, it will be scanned. If it has default credentials, it will be compromised.

### Scoring

| Score | Criteria |
|-------|----------|
| PASS | Secrets managed properly, OWASP basics covered, input validated |
| CONDITIONAL | Some gaps but no user data at risk — fix before going public |
| FAIL | Secrets in code, no input validation, running as root, or "I'll secure it later" |

---

## Gate 6: Is the Cost Right?

**Core question:** Are you burning money, tokens, and time proportional to the value you're creating?

### Checklist

- [ ] You know the actual cost of your AI/API usage (not a guess)
- [ ] You've compared the cost of building vs buying/using an existing solution
- [ ] You have a budget cap and will stop if you hit it
- [ ] You've calculated cost per user/request at scale (not just for demos)
- [ ] Rate limits are in place (both API-side and your own)

### AI/LLM Token Economics

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

### Time Cost

1. **How many hours will this take to build?** Be honest. Multiply your estimate by 3.
2. **What else could you do with that time?** Opportunity cost is real.
3. **Is "learning" the actual goal?** That's valid — but budget for it honestly.

### Infrastructure Cost

- [ ] Can this run on a free tier? (Vercel, Fly.io, Railway free plans)
- [ ] Do you actually need a database server or would SQLite + file storage work?
- [ ] Are you paying for services you don't need yet? (monitoring, CDN, managed DB)
- [ ] What's the monthly cost at 0 users? If it's > $0 with no users, question everything.

### Scoring

| Score | Criteria |
|-------|----------|
| PASS | Costs are known, budgeted, proportional to value, and rate-limited |
| CONDITIONAL | Costs are estimated but not measured — needs monitoring before scaling |
| FAIL | No idea what you're spending, no budget, or cost exceeds any plausible value |

---

## Gate 7: Does It Have to Be Done This Way?

**Core question:** Is your chosen approach the right one, or just the first one you thought of?

### Checklist

- [ ] You've considered at least 3 alternative approaches
- [ ] You can articulate WHY this approach over the alternatives
- [ ] You've identified what you'd lose by choosing a different approach
- [ ] The approach matches the problem's actual constraints (not imagined ones)
- [ ] You're not locked into a path just because you already started

### The Alternatives Matrix

| Approach | Pros | Cons | Effort | Risk |
|----------|------|------|--------|------|
| Your current approach | | | | |
| Alternative 1: | | | | |
| Alternative 2: | | | | |
| Do nothing | | | | |

**"Do nothing" must always be an option.** If doing nothing is viable, your project needs to justify its existence against inaction.

### Critical Questions

**Could this be simpler?**
1. Does this need an app, or would a spreadsheet work? Seriously.
2. Does this need a backend, or could it be client-side only?
3. Does this need AI, or would a regex/rule-based approach work? Not everything needs an LLM.
4. Does this need real-time, or is a cron job + static page fine?
5. Does this need a custom solution, or does a SaaS product cover 90% of it?

**Could this be done differently?**
1. Are you building a platform when you need a script?
2. Are you building an API when a CLI would do?
3. Are you building a dashboard when an email report would do?
4. Are you automating something that happens once a month? Manual might be fine.
5. Are you building for scale you'll never reach?

**Are your constraints real?**
1. "It needs to be fast" — How fast? Have you measured the current speed? Is it actually slow?
2. "It needs to handle millions of requests" — Will it ever? Really?
3. "It needs to be cross-platform" — Who uses it on platforms other than yours?
4. "It needs to be offline-capable" — When was the last time you were offline?
5. "It needs a mobile app" — Or does a responsive website work?

### The Sunk Cost Trap

If you've already started and this gate makes you doubt: code you've written is not a reason to continue (sunk cost), time you've spent is not an investment to protect (it's gone), and switching costs are real but often smaller than the cost of continuing wrong. The best time to pivot was yesterday. The second best time is now.

### Scoring

| Score | Criteria |
|-------|----------|
| PASS | This approach is the simplest viable path, with alternatives considered and rejected for clear reasons |
| CONDITIONAL | Better approaches might exist — research needed before committing |
| FAIL | You chose the first/coolest approach without considering alternatives, or a clearly simpler option exists |
