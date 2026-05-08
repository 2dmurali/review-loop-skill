# review-loop-skill

[![skills.sh](https://skills.sh/b/2dmurali/review-loop-skill)](https://skills.sh/2dmurali/review-loop-skill)

A reusable AI agent skill that implements an **iterative worker-reviewer cycle** to produce higher quality output through structured critique and revision.

Works with any AI agent that supports subagent spawning (Cursor, Claude, Windsurf, etc.).

---

## What it does

Instead of trusting a first draft, the agent:
1. Does the work (writes code, spec, doc, etc.)
2. Spawns a **separate critic subagent** with a fresh context
3. The critic scores the work **1–10** with specific, actionable feedback
4. The agent revises based on the feedback
5. Repeats until the **quality gate is met** (default: 8/10)

**Result:** Fewer bugs, better specs, more robust implementations — without needing a human reviewer in the loop.

---

## Quick install

```bash
npx skills add 2dmurali/review-loop-skill
```

Or clone and copy manually:
```bash
git clone git@github.com:2dmurali/review-loop-skill.git
cp -r review-loop-skill/review-loop ~/.cursor/skills/
```

---

## Usage

Just mention it in your prompt:

```
implement the payment service, use review-loop
```
```
run review-loop on the auth module I just wrote
```
```
use review-loop, quality gate 9, thorough
```

---

## Defaults

| Setting | Default |
|---------|---------|
| Min loops | 2 |
| Max loops | 4 |
| Quality gate | 8/10 |

Override inline: `"use review-loop, gate 9, max 5 loops"`

---

## Folder structure

```
review-loop-skill/
└── review-loop/
    └── SKILL.md
```

---

## License

MIT — free to use, adapt, and redistribute with any AI tool or platform.
