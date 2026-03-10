# doubt.md

A ruthless self-interrogation framework for engineering projects. Before you write code, spend tokens, or burn a weekend — run your idea through 7 gates.

> "The first principle is that you must not fool yourself — and you are the easiest person to fool." — Feynman

## The Problem

You had a great idea at 2 AM. You started coding. Three weekends and $40 in API tokens later, you realize:
- It already exists
- Nobody needs it
- A spreadsheet would have worked
- Your `.env` was committed on day one

**doubt.md** forces you to confront these questions **before** you build.

## The 7 Gates

Every idea must survive all gates. If it fails one, it's not dead — but you must document why you're proceeding anyway.

| # | Gate | Question |
|---|------|----------|
| 1 | [Originality](01-does-it-exist.md) | Am I reinventing the wheel? |
| 2 | [Necessity](02-is-it-needed.md) | Does anyone actually need this? |
| 3 | [Effectiveness](03-is-it-effective.md) | Will it actually solve the problem? |
| 4 | [Engineering](04-is-it-sound.md) | Is the approach technically sound? |
| 5 | [Security](05-is-it-secure.md) | Will this get hacked in minutes? |
| 6 | [Cost](06-is-the-cost-right.md) | Am I burning money for nothing? |
| 7 | [Approach](07-is-this-the-way.md) | Does it HAVE to be done this way? |

## Usage

### As an Obsidian vault
```
git clone https://github.com/YOUR_USERNAME/doubt.md.git
```
Open the folder as a vault in Obsidian. Notes are interlinked with `[[wikilinks]]` and work with graph view.

### As a checklist
Copy [`templates/DOUBT-SESSION.md`](templates/DOUBT-SESSION.md) and fill it in for your project. Score each gate as **PASS**, **CONDITIONAL**, or **FAIL**. If 2+ gates fail, stop and rethink.

### As a team exercise
Run a doubt session before greenlighting a new project. Assign each gate to a different person. The person most excited about the idea should NOT evaluate Gate 2 (Necessity).

## What This Is Not

- **Not a project management framework.** This is pre-project — use it before you commit to building.
- **Not a novel methodology.** It's an opinionated remix of [Critical Design Reviews](https://www.dau.edu/acquipedia-article/critical-design-review-cdr), lean startup validation, pre-mortem analysis, and [Architecture Decision Records](https://adr.github.io/).
- **Not a replacement for user research.** If Gate 2 makes you doubt, go talk to actual users instead of filling in more markdown.

## Structure

```
doubt.md/
├── DOUBT.md                        # Index — start here
├── 01-does-it-exist.md             # Gate 1: Originality
├── 02-is-it-needed.md              # Gate 2: Necessity
├── 03-is-it-effective.md           # Gate 3: Effectiveness
├── 04-is-it-sound.md               # Gate 4: Engineering
├── 05-is-it-secure.md              # Gate 5: Security
├── 06-is-the-cost-right.md         # Gate 6: Cost
├── 07-is-this-the-way.md           # Gate 7: Approach
└── templates/
    └── DOUBT-SESSION.md            # Fill-in template for evaluating a project
```

## Contributing

Open an issue or PR. If you've used this framework and it saved you from a bad project (or failed to stop a good one), share the story.

## License

[MIT](LICENSE)
