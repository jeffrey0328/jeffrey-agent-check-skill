# Project norms & checks

A project’s **governance files** are created and maintained per the current agent app’s project-rules spec plus `preferences.md`. The canonical layout and writing rules live in `jeffrey-agent-workflow-skill/references/project-rules.md` — this file routes there and adds the check standard; it does not restate the layout. Product code is out of scope.

**读法:** § Governance files for what is covered; § Check list for the gate.

## Governance files

| File | Standard |
|------|----------|
| `AGENTS.md` (project root) | Neutral, agent-agnostic; required-skill gates point at skills that exist; startup order and task rules follow `project-rules.md` |
| `.agents/` + agent adapter files | Only content that one agent alone needs; layout per `project-rules.md` §1.0 and `content-boundaries.md` § Where agent-specific content lives |
| `.mdc` rules | Format and gate per `project-rules.md` § 2–3 |
| Human pages (`README.md` / `README-EN.md` / `DEVLOG.md`) | Shape, language and currency per `jeffrey-agent-workflow-skill` § Projects |
| Skill pointers | Every pointer resolves to an existing skill; spoken-name catalog stays in each skill’s `description`, not duplicated in rules |

## Check list (full)

| Check | Pass |
|-------|------|
| Layout | `AGENTS.md` neutral + `.agents/` for agent-only content, per `project-rules.md` |
| Required-skill gates | Every must-load skill named in `AGENTS.md` exists and is loadable in the current app |
| Pointers | All file/skill pointers resolve; no leftover path to a renamed skill |
| Human pages | per `jeffrey-agent-workflow-skill` § Projects |
| File language | per `jeffrey-agent-workflow-skill` § Projects |
| Writing norms | Positive/negative pairing per `skill-authoring.md` § Positive / negative norms; no machine-local values in committed files |
| Freshness | Rules that cite code paths/symbols still match the code (verify before relying) |

Quick check (before use): required-skill gates loadable, pointers resolve, no machine-local values, `AGENTS.md` startup order readable, file language per § Check list.

## Must

- Check governance files against `project-rules.md` and the current app’s spec before working under them or editing them.
- Keep project human pages and the progress log current: `jeffrey-agent-workflow-skill` § Projects.

## Must not

- Put agent-only content into the neutral `AGENTS.md` or other shared parts. *(← Must: layout per project-rules.md — agent-only content lives in `.agents/` / adapter files)*
- Restyle product code as part of a governance check. *(← scope is governance files; product code is out of scope)*