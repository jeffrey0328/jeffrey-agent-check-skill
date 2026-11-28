# Jeffrey’s standing preferences

The second half of the check standard (the first half is the current agent app’s spec). These are Jeffrey’s stated preferences that apply across agents and projects; a domain norms file plus this page is what a full check measures against. When a preference here conflicts with a project’s `AGENTS.md`, the project file wins inside that project — report the conflict.

**读法:** scan the section matching the domain being checked; § Adding a preference when Jeffrey states a new one.

## Naming & creation

- Global skill id and prefixed-name proposal: `skill-authoring.md` § Global skill id.
- Before creating any skill files: confirm the exact name, then ask whether to create a git repo and whether private or public. Never infer a default from silence or from a previous skill.
- Rule vs Skill triage and confirmation: `content-boundaries.md` § Rule vs Skill triage.

## Skill shape & language

- Skill shape, companion files, 叫法 and file language: `skill-authoring.md` and `hub-norms.md`. Project human pages and progress log: `jeffrey-agent-workflow-skill` § Projects. Conversation language: `jeffrey-agent-workflow-skill` § Language.
- Rewrite policy: each skill's `kind.txt` (`skill-authoring.md` § Skill kind).

## Working style

- Question cards, context-on-card, one-card-one-question, repeat-avoidance: `jeffrey-agent-workflow-skill` § Asking Jeffrey.
- Memory-update announcements and profile auto-maintenance: `jeffrey-agent-workflow-skill` § Memory updates.
- Feedback and reports describe every change or gap by its content and purpose in plain language, never by bare file name — Jeffrey does not memorize file roles. A file path may follow as a trailing hint, never as the subject of the finding.
- Scriptable checks through the fixed gate script: `agent-check.md` § Flow.
- One conversation one thing; unrelated input: `jeffrey-agent-workflow-skill` § Unrelated input.
- Edit the original in place: `jeffrey-agent-workflow-skill` § Updating skills.
- Tell-then-ask before push: `jeffrey-agent-workflow-skill` § Updating skills.
- Jeffrey's decisions asked before execution: `jeffrey-agent-workflow-skill` § Workflow.

## Content hygiene

- Machine-local values in committed content: `agent-check.md` (machine-local values check row).
- MCP config travels as sanitized `*.example.json` snippets only; never commit auth files or API keys.
- Plugins: only the sanitized lock inventory travels; install output and per-machine runtime state never get committed.

## Product & UI taste

- No helper captions or process-restating microcopy unless Jeffrey asks; follow `jeffrey-web-dev-skill` hub-norms for web UI.
- Projects keep a Chinese `README.md` with an English `README-EN.md` companion and a Chinese `DEVLOG.md`: `jeffrey-agent-workflow-skill` § Projects.

## Adding a preference

When Jeffrey states a new standing preference: record it here at the fitting section (in place, not appended), in English, agent-agnostic wording; then check whether existing covered content contradicts it and report what needs updating. A preference stated for one project only goes to that project’s `AGENTS.md`, not here.