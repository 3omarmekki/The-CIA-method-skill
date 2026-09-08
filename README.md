# The CIA Challenge Framework

> An open **Agent Skill** that stress-tests any idea, plan, or technical approach the way structured analytic tradecraft does — reducing bias and stopping you from locking onto the first plausible story before you spend time, code, or budget.

![license](https://img.shields.io/badge/license-MIT-F7A901?style=flat-square)
![standard](https://img.shields.io/badge/Agent%20Skills-open%20standard-EAD9BC?style=flat-square)
![agents](https://img.shields.io/badge/agents-10%2B-3A3F55?style=flat-square)

![CIA Challenge Framework pipeline](assets/banner.svg)

---

## What it does

You paste an idea. The agent runs five techniques **in order** — no skipping, no softening — and ends with a verdict.

| # | Technique | What the agent does |
|---|-----------|---------------------|
| **01** | **Key assumptions check** | Lists the assumptions the idea depends on. Marks which are untested, uncertain, or fragile. States what evidence would confirm or break each one. *Hidden assumptions are where bad conclusions hide.* |
| **02** | **Generate alternatives** | Forces at least 3 real alternatives: another explanation, a simpler approach, and a do-nothing option. *The first answer is usually just the easiest answer.* |
| **03** | **Competing hypotheses** | Frames several plausible conclusions, then scores how well the evidence supports or contradicts each one — weighting evidence that *disconfirms* the favorite. *Try to disprove the lead theory first.* |
| **04** | **What-if analysis** | Asks what happens if the core belief is wrong: failure scenarios, second-order effects, overlooked edge cases. *If the opposite breaks you, you were never ready.* |
| **05** | **Red-team the idea** | Assigns hostile roles — skeptical customer, operator, CFO, regulator, competitor — and attacks from each. *A strong idea survives pressure, not praise.* |

The whole run follows one loop:

```
assume  →  compare  →  invert  →  attack  →  decide
```

### Working with AI

- The agent answers as separate roles, one at a time.
- Every attack cites *which assumption* is being challenged.
- Every pass closes with the single highest-risk failure plus the next test to run.
- No flattery. If the idea survives, it says why — and what it would take to break it.

### The deliverable

The skill always ends with:

1. **The highest-risk failure**
2. **The one assumption that would break the idea**
3. **The next concrete test to run**
4. **A verdict** — `go`, `go with conditions`, or `don't`

---

## Install

Two ways. Both are copy-paste on any OS.

### Option A — universal copy (works everywhere)

The skill lives in a self-contained `cia/` folder, so installing it is just copying that folder into any agent's skills directory (see the table below for the exact path).

**macOS / Linux**

```bash
git clone --depth 1 https://github.com/3omarmekki/The-CIA-method-skill.git /tmp/cia-skill
mkdir -p ~/.agents/skills/cia
cp /tmp/cia-skill/cia/SKILL.md ~/.agents/skills/cia/SKILL.md
```

**Windows (PowerShell)**

```powershell
git clone --depth 1 https://github.com/3omarmekki/The-CIA-method-skill.git $env:TEMP\cia-skill
New-Item -ItemType Directory -Force "$env:USERPROFILE\.agents\skills\cia"
Copy-Item "$env:TEMP\cia-skill\cia\SKILL.md" "$env:USERPROFILE\.agents\skills\cia\SKILL.md"
```

The `~/.agents/skills/` (and `~/.config/agents/skills/`) locations are the open interoperable home — they are read by Gemini CLI, Kimi Code CLI, Cursor, Codex, and several others.

### Option B — `npx skills add` (auto-detects your agents)

If you have [Node.js](https://nodejs.org) and one of the [skills CLIs](https://github.com/vercel-labs/skills):

```bash
npx skills add 3omarmekki/The-CIA-method-skill
```

The CLI detects which agent is installed and drops the skill into the right directory for you. On a machine with several agents, run it once per agent.

---

## Where the skill goes, per agent

| Agent | Global (all projects) | Project (this repo only) | Invoke |
|---|---|---|---|
| **OpenCode** | `~/.config/opencode/skills/cia/` | `.opencode/skills/cia/` | "CIA it: …" |
| **Codex (OpenAI)** | `~/.codex/skills/cia/` | `.codex/skills/cia/` | "CIA it: …" |
| **Claude Code** | `~/.claude/skills/cia/` | `.claude/skills/cia/` | `/` menu or "CIA it: …" |
| **Gemini CLI** | `~/.gemini/skills/cia/` | `.gemini/skills/cia/` | auto ("CIA it: …") |
| **Kimi Code CLI** | `~/.kimi/skills/cia/` | `.kimi-code/skills/cia/` | `/skill:cia` |
| **Cursor** | `~/.cursor/skills/cia/` | `.cursor/skills/cia/` | `/` → `cia`, or `@cia` |
| **GitHub Copilot** | — | `.github/copilot/skills/cia/` | auto / `/cia` |
| **Any SKILL.md agent** | `~/.agents/skills/cia/` | `.agents/skills/cia/` | auto |

> Only `SKILL.md` is required. Supporting `scripts/`, `references/`, `assets/` may live beside it — place the whole `cia` folder when copying.

<details>
  <summary><strong>Detailed setup — OpenCode</strong></summary>

**macOS / Linux**

```bash
mkdir -p ~/.config/opencode/skills/cia
cp /tmp/cia-skill/cia/SKILL.md ~/.config/opencode/skills/cia/SKILL.md
# or project-scoped:
mkdir -p .opencode/skills/cia
cp /tmp/cia-skill/cia/SKILL.md .opencode/skills/cia/SKILL.md
```

**Windows (PowerShell)**

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.config\opencode\skills\cia"
Copy-Item "$env:TEMP\cia-skill\cia\SKILL.md" "$env:USERPROFILE\.config\opencode\skills\cia\SKILL.md"
```

**Verify:** start `opencode` and ask *"list your available skills"* — `cia` should appear. **Use:** `CIA it: <paste your idea>`.
</details>

<details>
  <summary><strong>Detailed setup — Codex (OpenAI)</strong></summary>

**macOS / Linux**

```bash
mkdir -p ~/.codex/skills/cia
cp /tmp/cia-skill/cia/SKILL.md ~/.codex/skills/cia/SKILL.md
# or project-scoped:
mkdir -p .codex/skills/cia
cp /tmp/cia-skill/cia/SKILL.md .codex/skills/cia/SKILL.md
```

**Windows (PowerShell)**

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.codex\skills\cia"
Copy-Item "$env:TEMP\cia-skill\cia\SKILL.md" "$env:USERPROFILE\.codex\skills\cia\SKILL.md"
```

**Verify:** start `codex`, type `$skill-installer list`. **Use:** `CIA it: <paste your idea>`.
</details>

<details>
  <summary><strong>Detailed setup — Claude Code</strong></summary>

**macOS / Linux**

```bash
mkdir -p ~/.claude/skills/cia
cp /tmp/cia-skill/cia/SKILL.md ~/.claude/skills/cia/SKILL.md
# or project-scoped:
mkdir -p .claude/skills/cia
cp /tmp/cia-skill/cia/SKILL.md .claude/skills/cia/SKILL.md
```

**Windows (PowerShell)**

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.claude\skills\cia"
Copy-Item "$env:TEMP\cia-skill\cia\SKILL.md" "$env:USERPROFILE\.claude\skills\cia\SKILL.md"
```

**Verify:** type `/` in the Claude Code prompt — `cia` shows in the skills menu. **Use:** `CIA it: <paste your idea>`.
</details>

<details>
  <summary><strong>Detailed setup — Gemini CLI</strong></summary>

The quickest path uses Gemini's own installer (no Node needed):

**macOS / Linux / Windows**

```bash
# installs globally (use --scope workspace for one project)
gemini skills install https://github.com/3omarmekki/The-CIA-method-skill.git
```

**Or manually — macOS / Linux**

```bash
mkdir -p ~/.gemini/skills/cia
cp /tmp/cia-skill/cia/SKILL.md ~/.gemini/skills/cia/SKILL.md
```

**Or manually — Windows (PowerShell)**

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.gemini\skills\cia"
Copy-Item "$env:TEMP\cia-skill\cia\SKILL.md" "$env:USERPROFILE\.gemini\skills\cia\SKILL.md"
```

**Verify:** inside `gemini`, run `/skills list` (or `/skills reload` after installing). **Use:** it auto-triggers on *"CIA it: …"*.
</details>

<details>
  <summary><strong>Detailed setup — Kimi Code CLI</strong></summary>

**macOS / Linux**

```bash
mkdir -p ~/.kimi/skills/cia
cp /tmp/cia-skill/cia/SKILL.md ~/.kimi/skills/cia/SKILL.md
# or project-scoped:
mkdir -p .kimi-code/skills/cia
cp /tmp/cia-skill/cia/SKILL.md .kimi-code/skills/cia/SKILL.md
```

**Windows (PowerShell)**

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.kimi\skills\cia"
Copy-Item "$env:TEMP\cia-skill\cia\SKILL.md" "$env:USERPROFILE\.kimi\skills\cia\SKILL.md"
```

Kimi also reads `~/.agents/skills/`, `~/.claude/skills/` and `~/.codex/skills/`, so an install there works too.

**Verify / use:** type `/skills` to list, or load it explicitly with `/skill:cia <paste your idea>`.
</details>

<details>
  <summary><strong>Detailed setup — Cursor</strong></summary>

**macOS / Linux**

```bash
mkdir -p ~/.cursor/skills/cia
cp /tmp/cia-skill/cia/SKILL.md ~/.cursor/skills/cia/SKILL.md
# or project-scoped:
mkdir -p .cursor/skills/cia
cp /tmp/cia-skill/cia/SKILL.md .cursor/skills/cia/SKILL.md
```

**Windows (PowerShell)**

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.cursor\skills\cia"
Copy-Item "$env:TEMP\cia-skill\cia\SKILL.md" "$env:USERPROFILE\.cursor\skills\cia\SKILL.md"
```

Cursor also auto-loads from `.claude/skills/` and `.codex/skills/` for compatibility. **Use:** type `/` in agent chat and pick `cia`, or attach once with `@cia`.
</details>

<details>
  <summary><strong>Detailed setup — GitHub Copilot</strong></summary>

Project-scoped only:

**Command line (any OS)** — commit the skill into the repo:

```bash
mkdir -p .github/copilot/skills/cia
cp /tmp/cia-skill/cia/SKILL.md .github/copilot/skills/cia/SKILL.md
git add .github/copilot/skills/cia
git commit -m "Add CIA skill for Copilot"
git push
```

Every contributor gets it automatically. **Use:** `CIA it: <paste your idea>` in Copilot chat.
</details>

---

## Usage

Nothing to remember — every agent already knows the trigger phrases:

```
CIA it: <paste your idea, plan, or technical approach>
CIA this before we build it: [link or paste]
What's the highest-risk assumption here? Run the full challenge.
```

The framework is deliberately hostile. If you want the *nice version* of the feedback, this is the wrong skill.

---

## Design & attribution

- **Name.** "CIA" is a reference to the structured analytic techniques whose lineage this framework follows — the skill is **not affiliated with, endorsed by, or connected to the Central Intelligence Agency**.
- **Techniques.** The five techniques compose real, declassified, public-domain material:
  - CIA *Tradecraft Primer: Structured Analytic Techniques for Improving Intelligence Analysis* (2009)
  - Richards J. Heuer Jr., *Psychology of Intelligence Analysis* (Center for the Study of Intelligence, 1999) — the source of *Analysis of Competing Hypotheses*
- **What's original here.** The composition of the five techniques into one ordered critique sequence, the "Working with AI" execution protocol (separate roles, cite the challenged assumption, close every pass, verdict), and the output contract.

## License

[MIT](LICENSE) — reuse, remix, publish. Keep the attribution note. Built with the open [Agent Skills](https://agentskills.io) standard, so a single `SKILL.md` runs on 10+ agents.