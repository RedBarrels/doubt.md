# DOUBT Session: doubt.md

**Date:** 2026-03-10
**Author:** Claude Opus 4.6 (evaluating its own output — take with a grain of salt)
**One-line description:** A markdown-based 7-gate framework for critically evaluating engineering projects before building them.

---

## Gate Results

| Gate | Score | Confidence | Notes |
|------|-------|------------|-------|
| [[01-does-it-exist\|Originality]] | ⬜ CONDITIONAL | High | Similar things exist in fragments |
| [[02-is-it-needed\|Necessity]] | ⬜ CONDITIONAL | Medium | Useful for the author, unproven for others |
| [[03-is-it-effective\|Effectiveness]] | ⬜ CONDITIONAL | Medium | Only effective if actually used |
| [[04-is-it-sound\|Engineering]] | ✅ PASS | High | It's markdown files — hard to over-engineer |
| [[05-is-it-secure\|Security]] | ✅ PASS | High | No attack surface |
| [[06-is-the-cost-right\|Cost]] | ⬜ CONDITIONAL | High | Spent ~$3-5 in tokens creating this. Borderline. |
| [[07-is-this-the-way\|Approach]] | ⬜ CONDITIONAL | Medium | Obsidian-specific choice has trade-offs |

**Overall verdict:** ⬜ GO WITH CONDITIONS

---

## Gate 1: Does It Already Exist?

**Similar projects found:**

1. **[ai-idea-validator](https://github.com/RCushmaniii/ai-idea-validator)** — GPT-4o-powered idea validation with 23 questions across 4 sections (competitive moats, platform risk, lock-in, failure modes). Outputs KILL/FLIP/BUILD/BET verdict. **Has contradiction detection** — compares numeric self-scores against written answers to catch optimism bias. This is arguably smarter than doubt.md's manual approach.

2. **[Architecture Decision Records (ADR)](https://adr.github.io/)** — Established format for documenting engineering decisions with context, decision, status, and consequences. Widely adopted. Covers Gate 4 and Gate 7 territory.

3. **[Pre-mortem methodology](https://github.com/microsoft/prompts-for-edu/blob/main/Students/Prompts/Team%20Pre-mortem%20Coach.MD)** — Microsoft's team pre-mortem coach. Based on Klein & Mitchell research. Covers "assume the project failed — why?" which is essentially what all 7 gates ask.

4. **[Postmortem templates](https://github.com/dastergon/postmortem-templates)** — 100+ stars. Industry-standard post-incident format. Not pre-project, but the structure is proven.

5. **[ValidatorAI.com](https://validatorai.com/startup-idea-validation-checklist-prompts-tools-and-more)** — Full startup validation checklist with AI prompts. Covers market, competition, and feasibility.

6. **[Obsidian decision templates](https://publish.obsidian.md/manuel/Templates/Decision+Template)** — Existing Obsidian-native decision documentation.

**Key differentiator (if any):**

doubt.md combines security audit + token cost analysis + engineering review + necessity check in one place. The ai-idea-validator is business-focused (moats, lock-in). ADRs are post-decision. Pre-mortems are freeform. doubt.md is the only one that asks "is your .env in .gitignore?" alongside "does anyone need this?"

But honestly? The differentiation is thin. You could get 80% of this by combining an ADR template + the ai-idea-validator + a security checklist.

**Verdict: CONDITIONAL** — The combination is somewhat novel. The individual components are not.

---

## Gate 2: Is It Needed?

**Target user (specific):** Solo developers / small teams who use Claude Code or similar AI coding assistants, tend to start projects impulsively, and have been burned by wasted effort before.

**Evidence of need:**
- The author's own project history shows $37.59 spent on AI-Inventory in one session, $14.46 on Hecate — suggesting a pattern of diving in without cost analysis
- Reddit/HN are full of "I built X and nobody used it" posts
- No hard evidence that anyone OTHER than the author wants this specific framework

**What they do today without this:** They either don't evaluate at all (most common), or do ad-hoc mental evaluation that suffers from confirmation bias — exactly the kind of bias the ai-idea-validator is specifically designed to detect and doubt.md is NOT.

**Honest assessment:** This is a vitamin, not a painkiller. People who need this framework the most are the ones least likely to use it — because the dopamine of starting a new project beats the discipline of evaluating one. The people disciplined enough to use this framework probably don't need it.

**Verdict: CONDITIONAL** — Useful for the author as a personal habit tool. Unproven demand from anyone else. The "portfolio project or product?" question from Gate 2 applies here: this is closer to a blog post than a product.

---

## Gate 3: Is It Effective?

**Success metric:** A user runs the doubt session, gets a NO-GO verdict, and avoids a bad project. Or gets a GO verdict with conditions that improve the project.

**Can we measure this?** Not really. There's no feedback loop built in. No telemetry (good for privacy, bad for validation). You'd have to trust self-reporting.

**Minimum viable version:** Could have been a single README with 7 questions. The multi-file Obsidian vault with templates, scoring, and wikilinks is already past MVP — it's a V2 of something that hasn't proven V1.

**The demo trap applies:** This framework looks great as a GitHub repo. The graph view in Obsidian is satisfying. But looking at a nice graph is not the same as ruthlessly doubting your idea. The format might give a false sense of rigor — filling in checkboxes feels productive even if you're lying to yourself on every answer.

**Key weakness:** No contradiction detection. The ai-idea-validator catches when your numeric scores don't match your written answers. doubt.md trusts the user to be honest, which is exactly the problem it's trying to solve.

**Verdict: CONDITIONAL** — The structure is sound, but effectiveness depends entirely on user honesty, which is the one thing you can't template.

---

## Gate 4: Is the Engineering Sound?

**Architecture:** It's markdown files in a folder. There is no architecture. This is correct.

**Tech stack:** Markdown + Obsidian wikilinks. Zero dependencies. Zero build steps. Zero runtime. This is the right call for static content.

**Engineering hygiene:**
- [x] `.mcp.json` is in `.gitignore` (API key not leaked)
- [x] `.claude/` is in `.gitignore`
- [x] No dependencies to pin
- [x] MIT license included
- [x] `.DS_Store` ignored

**The one concern:** The Obsidian REST API key was visible in the screenshot the author shared in the conversation. If that screenshot is ever shared publicly, the key is compromised. It's a local-only key so blast radius is low — but it's ironic for a framework that includes a security gate.

**Verdict: PASS** — You can't over-engineer markdown. The simplicity is genuine.

---

## Gate 5: Is It Secure?

**Blast radius if hacked:** Zero. It's a collection of `.md` files. No backend, no API, no user data, no auth, no deployment. The only attack surface was the Obsidian REST API key in the screenshot, which is local-only.

**OWASP quick scan:** Not applicable — there's nothing to hack.

**Secrets management:** The `.mcp.json` with the API key is properly gitignored.

**Verdict: PASS** — The most secure software is software that doesn't run.

---

## Gate 6: Is the Cost Right?

**Build time:** ~30 minutes of Claude Opus 4.6 time.

**Token cost estimate:**
- This session has involved ~15-20 API calls
- Mix of Opus (writing) and Haiku (search/exploration)
- Estimated cost: $3-5 for the full session
- That's in the same ballpark as a fancy coffee

**Monthly running cost:** $0. It's static files.

**Was it worth it?**

Honest answer: borderline. The same framework could have been written as a single blog post in 20 minutes by a human. The multi-file Obsidian structure, wikilinks, and templates add convenience but not substance. The web research to validate originality was genuinely useful — without it, we wouldn't know about ai-idea-validator or the existing Obsidian decision templates.

**The meta-irony:** This doubt session cost additional tokens on top of the creation cost. Doubting is not free. If you doubt every project this thoroughly, the overhead adds up. There should probably be a "quick doubt" lightweight version for small projects.

**Verdict: CONDITIONAL** — Cost is low in absolute terms. But the value-per-dollar is questionable given that similar content exists freely.

---

## Gate 7: Does It Have to Be Done This Way?

**Alternatives considered:**

| Approach | Pros | Cons | Effort | Risk |
|----------|------|------|--------|------|
| Obsidian vault (current) | Pretty graph, interlinked, offline | Obsidian-specific, intimidating for non-users | Medium | Low |
| Single README checklist | Universal, minimal, forkable | No structure for detailed answers | Low | Low |
| Web app with AI scoring | Could detect contradiction/bias like ai-idea-validator | Way more complex, needs hosting, costs money | High | High |
| Blog post | Reaches more people, SEO | Not interactive, can't fill in answers | Low | Low |
| Do nothing | Free | Doesn't solve the problem | Zero | Zero |

**Why this approach wins:** It doesn't clearly win. A single README with 7 sections and checkboxes would reach more people and be easier to adopt. The Obsidian vault is prettier but limits the audience to Obsidian users.

**The honest answer:** This was built as an Obsidian vault because the author uses Obsidian and wanted to try the MCP integration. That's a valid reason — but it's "I wanted to try the tech" not "this is the best format for the content."

**Simpler alternatives that might work better:**
1. A GitHub Gist with one file
2. A `DOUBT.md` file you drop into any project repo (like how `CONTRIBUTING.md` works)
3. A GitHub Issue template that teams fill out before starting new projects

**Verdict: CONDITIONAL** — The approach works but isn't justified as the best one. A portable single-file version should probably be the primary format, with the Obsidian vault as an optional expansion.

---

## Decision

**Proceeding?** Yes, with conditions.

**Conditions:**
1. **Add a single-file version** — a standalone `DOUBT.md` that can be dropped into any repo without needing Obsidian
2. **Acknowledge prior art** — link to ai-idea-validator, ADRs, and pre-mortem methodology in the README. Don't pretend this is novel.
3. **Add a "quick doubt" lightweight version** — 7 yes/no questions for small projects that don't warrant the full session
4. **Rotate the Obsidian API key** — it was visible in a screenshot during this session
5. **Don't spend more tokens polishing this** — it's good enough. The risk is now over-investment, not under-investment.

**Review date:** 2026-04-10 (one month). If nobody stars/forks the repo by then, it validated its own Gate 2 failure.

**Lessons for next time:**
- The framework caught real issues when applied to itself (thin differentiation, unproven need, format lock-in)
- The lack of contradiction detection is a genuine gap vs ai-idea-validator
- Meta-evaluation is useful but expensive — consider making it a habit only for projects above a cost threshold
