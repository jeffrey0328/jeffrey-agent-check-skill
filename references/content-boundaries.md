# Content boundaries — where content goes

Single dispatcher for placement decisions: which of the four homes a recordable item goes to, Rule-vs-Skill triage and rule creation, and judging which agent app owns a passage. Domain norms stay in their own files; this file decides placement and routes.

Four homes: **Skill**, **user-level AGENTS.md** (agent config home), **project rules** (project `AGENTS.md` / `.agents/` / `.mdc`), **auto-memory** (user scope and project scope — 记忆 and Memory are this one mechanism, two scopes).

**读法:** § Decision tree for which home; § Rule vs Skill triage + § Rule creation workflow for behavior guidance; § Judging agent-specific content for shared-vs-app ownership; § Precedence for conflicts.

## Decision tree (apply in order, stop at the first match)

1. **Not durable?** One-off conversation state, task progress, or a one-off investigation result → do not persist; keep it in the conversation, plan, or task. (`memory-norms.md` § Write)
2. **A fact, not a directive?**
   - About Jeffrey (role, decision tendency, language habit, preference stated as fact) or an external-resource pointer → auto-memory **user scope**; decision/language facts go to the single-home profile `user-decision-language-profile`.
   - A project fact not derivable from code or git (decision, owner, absolute deadline) → auto-memory **project scope**.
3. **A directive — how the agent must act?**
   - Applies only inside one project → project `AGENTS.md` / `.agents/` (`jeffrey-agent-workflow-skill/references/project-rules.md`).
   - Governs the agent config home itself (sync, plugin inventory, machine setup) → user-level `AGENTS.md`.
   - One agent app only → that app's config repo, or the owning skill's `<agent>/main` spec (`rule-norms.md` § Which home).
   - Shared procedure, workflow, or domain method → the owning skill; shared operating rules → `jeffrey-agent-workflow-skill`. Rule-vs-Skill triage and Jeffrey's confirmation come first (§ Rule vs Skill triage below).
4. **Both fact and directive in one statement?** Split: the directive to its skill/rule home, the fact as a one-line pointer in the profile. Full content lives in exactly one home (`memory-norms.md` § Write, single home).

Fact-vs-directive test: 「我偏好 X」/「我看重 X」 describes him → fact (memory). 「以后都要 X」/「不要 Y」 instructs the agent → directive (skill/rule). Skill-vs-rule ambiguity: the two core tests in § Rule vs Skill triage. When genuinely unsure, ask Jeffrey on a card.

**One kind, one skill (Jeffrey 2026-11-22):** the same content or same-kind content never lives in two skills — the owning skill carries it, every other skill points to it. A relevant skill is attached in the conversation anyway, so restating it elsewhere adds nothing. Restate only when the content must stand alone without the owning skill attached (rare); the default is a pointer.

## Rule vs Skill triage (required before creating)

When the user asks to create behavior guidance, **triage first**. Do **not** assume Rule or Skill — recommend, **wait for confirmation**, then create files.

| Signal | → Rule (project instructions) | → Skill (`SKILL.md` in a skill directory) |
|--------|--------------------------------|-------------------------------------------|
| **Nature** | Short declarative: "always X / never Y" | Multi-step workflow, domain knowledge, procedure |
| **Length** | Prefer &lt; 10 lines inline in `AGENTS.md`; longer → satellite `.md` | Up to ~500 lines `SKILL.md` + `references/` |
| **Scope** | Repo-wide (AGENTS) or path-scoped (satellite / optional `.mdc`) | Personal the current agent app's default skills path or the project skills path |
| **Trigger** | AGENTS pointer trigger, or project `globs` / `alwaysApply` on `.mdc` | Description match or explicit `@skill-name` |
| **Structure** | `AGENTS.md` ± any `.md` satellite ± optional project `.mdc` rules | Directory with `SKILL.md` plus the required companion files; the companion list lives in `skill-authoring.md` § File roles |
| **Examples** | Naming, error-handling, path-scoped plugin norms | PR workflow, migrations, domain codegen |
| **Analogy** | Traffic rules | Driving tutorial |

**Heuristic**: A **few bullets** (&lt; 10 lines) that apply repo-wide → **inline in `AGENTS.md`**. Same length but **one directory only**, or **≥ 10 lines** → satellite **`.md` anywhere** + AGENTS pointer with **trigger** — no fixed `docs/` layout; **`.mdc` only** for globs/alwaysApply. **Steps / deep workflow** → **Skill**. Details: `jeffrey-agent-workflow-skill/references/project-rules.md` §1.1.1.

**Core tests when skill-vs-rule is ambiguous (Jeffrey 2026-11-22):**

1. **Existing accumulation**: is there already a skill on this topic, with many entries accumulated in it? Yes → iterate that skill in place; do not spawn a parallel rule beside it.
2. **Step-writability**: can the content be written as step-by-step execution steps? Yes → skill (a procedure). No — it stays a declarative constraint that cannot be turned into steps → rule.

**Writing norms (Skills and Rules):** prefer affirmative Must; Must not only when it **contains/overlaps** a Must — `skill-authoring.md` § Positive / negative norms.

### Triage and confirmation workflow

1. **Analyze** the request: convention vs workflow.
2. **Recommend** Rule or Skill with one-sentence reason. Use AskQuestion when available: "Yes, create a Rule" / "Yes, create a Skill" / "Let me clarify".
3. **Wait for confirmation** — no files until confirmed.
4. **Execute**:
   - **Rule** → § Rule creation workflow below.
   - **Skill** → `skill-authoring.md`.

## Rule creation workflow

**A. Gather requirements**

1. Purpose  
2. Scope: repo-wide vs one directory / file type?  
3. Length estimate (&lt; 10 lines vs longer)

**B. Place per `jeffrey-agent-workflow-skill/references/project-rules.md` §1.1.1**

- **Both** &lt; 10 lines **and** not directory-only → write into **`AGENTS.md`** (no new satellite).
- Otherwise → satellite (**any `.md` path**; use `.mdc` **only** if globs/alwaysApply is needed) + **`AGENTS.md` pointer that states trigger + path (+ section) + how to read**.

**C. If writing `.mdc`** (optional — folder `.md` is fine when that fits better):

```markdown
---
description: Brief description of what this rule does
globs: **/*.ts
alwaysApply: false
---

# Rule Title

Rule content—concise, actionable, concrete examples.
```

**D. Constraints**

- One concern per rule; do not invent satellites for short repo-wide bullets.
- Actionable; good/bad examples; no narration that restates code.

**E. Frontmatter** (`.mdc` only)

| Field | Description |
|-------|-------------|
| `description` | Shown in rule picker |
| `globs` | Applies when matching files are open |
| `alwaysApply` | If `true`, every session |

**F. Patterns**

Always apply:

```yaml
---
description: Core coding standards for the project
alwaysApply: true
---
```

File-specific:

```yaml
---
description: TypeScript conventions
globs: "**/*.ts"
alwaysApply: false
---
```

## Where agent-specific content lives

Placement is owned by `rule-norms.md` § Which home (which repo / branch each kind of content sits in) and `skill-authoring.md` § Agent-specific spec file (how to write the per-agent spec). Content that only one agent app understands never goes into the shared parts; a shared skill mentions an agent-specific procedure only generically ("the current agent app's procedure") and points to where it lives.

## Judging agent-specific content

Run this judgment **automatically**, without being asked, whenever reading or applying project content (`AGENTS.md`, satellites, adapter files, per-app config directories) or skill content (hub, references, specs, scripts) — and before writing new content, to pick its home. Classify each passage into one of three owners: **shared**, **current app**, **another app**.

**Ownership tests** — a passage belongs to one app when any test names that app:

1. **Named**: it names the app concretely — its config directory, its spec file or base branch (the `.<agent>-customize/`, `<agent>-spec.md`, `<agent>/main` shapes with a real app name in them), its tools or APIs, or its install paths. The placeholder shapes alone are shared vocabulary, not naming.
2. **Executable only there**: following it requires a capability only that app has (its session/chat tools, deeplink or watcher mechanism, transcript format, UI).
3. **Homed**: it sits in that app's designated home per `rule-norms.md` § Which home — the app's branch/spec, the app's config repo, or the project's thin adapter file for that app.
4. **Values**: it carries identifiers only that app understands (its model keys or display names, its config keys).
5. **Model-related**: anything that specifies a model — model names or keys, tier→model maps, model-selection rules, model config — belongs to the app whose models it names (Jeffrey 2026-11-21).

A passage is **shared** when it is written app-agnostically ("the current agent app", or `<agent>`-style placeholders each app fills with its own name), sits in a shared home (default branch, neutral `AGENTS.md`, plugin), and any app can follow it as-is. Project data such as `.stride/` is shared.

**Litmus when unclear**: could another agent app follow this passage as-is, substituting nothing but its own name and paths for `<agent>`-style placeholders? Yes → shared. Only the current app can → current app. Only another app can → another app's.

**Dispatch-target naming is not host naming (Jeffrey 2026-11-24).** A passage naming an external CLI as the *target* of a shell dispatch (its commands, launcher/config paths, its model keys) is shared when any agent app can run it as-is — ownership tests 1 and 5 name the *host* app, not the dispatched tool. The naming exemption: `skill-authoring.md` § Agent-app names (external CLI dispatch targets).

**Act on the judgment**:

- Apply only shared + current-app content; read the current app's spec when it exists (`jeffrey-agent-workflow-skill` `SKILL.md` § Agent-specific spec index). Another app's rules are never applied to the current app, even when found inside a shared file.
- Write new agent-specific content into that app's home; keep shared content app-agnostic.
- On misplacement (one app's content sitting in a shared home), report both locations and move it per `rule-norms.md` § Which home; when it is unclear whether the placement is wrong or intentional, ask Jeffrey.
- When the classification itself is genuinely ambiguous, ask Jeffrey rather than guess.

## Precedence

- Inside a project, project `AGENTS.md` overrides a skill rule it explicitly covers; report the conflict (`preferences.md` header).
- A skill rule beats any memory restatement of it; memory keeps at most a pointer.
- User-level `AGENTS.md` governs the config directory itself, not project behavior.