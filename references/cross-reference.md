# Cross-reference map

Records **who references each tracked file** and whether the reference is to the **whole file (whole file)** or a **specific section (§)**.

**How to read:** Grep `^## ` for the target filename, then read only its row group.

## Maintenance rule (required)

- **Before editing** any file listed below (rename, move, delete, or rename/remove a `##` / `§` heading that appears in the Scope column), **read this record first** and update every listed referencer.
- **After editing**, keep this record in sync.
- **Scope of tracking:** all `references/*.md`, `examples/*`, `scripts/*`, and `kind.txt`. `SKILL.md` / `README.md` / `README-EN.md` appear as **referencers** only.

## references/

### cross-reference.md (this file)
| Referenced by | Scope |
|---------------|------|
| `SKILL.md` Route「Editing…」+ Always | whole file |
| `hub-norms.md` (top table + File index + Must + DoD) | whole file |
| `skill-authoring.md` § Exploration checklist | whole file |

### agent-check.md
| Referenced by | Scope |
|---------------|------|
| `SKILL.md` Commands + Route「Check before using or updating」+ Always | whole file + § When / § Depth |
| `hub-norms.md` File index + Must + DoD | whole file |
| `skill-authoring.md` header + § File roles + § Positive / negative norms + § Language | whole file (gate）+ § Depth |
| `plugin-norms.md` / `project-norms.md` / `rule-norms.md` / `memory-norms.md` headers + check lists | § Depth / § Flow |
| `sync-on-update.md` § Resident | whole file (full depth) |

### skill-authoring.md
| Referenced by | Scope |
|---------------|------|
| `SKILL.md` Route「Create/update Skill」+ Always「Authoring」| whole file + § Install prompt + § Global skill id + § Agent-specific spec file |
| `hub-norms.md` File index + Must + DoD | whole file + § File roles / § Spoken names / § Language / § Update log / § Global skill id / § Agent-specific spec file |
| `agent-check.md` § Domains | whole file |
| `plugin-norms.md` § Structure | § Agent-app names + whole file (bundled skills) |
| `project-norms.md` § Check list | § Positive / negative norms |
| `rule-norms.md` § Which home + § Check list | § Agent-specific spec file + § Positive / negative norms |
| `preferences.md` § Skill shape & language | § Skill kind |
| `sync-on-update.md` § Resident + § Companion sync | § Agent-specific spec file + § Synchronize companion files |
| sibling `jeffrey-agent-workflow-skill/SKILL.md` § Updating skills + § Projects | § Spoken names + § Language |
| `content-boundaries.md` § Rule vs Skill triage (Structure row + writing norms) + § Where agent-specific content lives | § File roles + § Agent-specific spec file + § Positive / negative norms |
| sibling `jeffrey-agent-config-skill` references (authoring pointer) | whole file |
| sibling `jeffrey-ue-dev-skill` (authoring pointer) | whole file |
| `examples/three-layer-layout.md` | § Three layers |
| `examples/agent-snippet.md` | § Prefer static / § Positive / negative norms |

### plugin-norms.md
| Referenced by | Scope |
|---------------|------|
| `SKILL.md` Route「Plugin」| whole file |
| `hub-norms.md` File index | whole file |
| `agent-check.md` § Covered content + § Domains | whole file |

### project-norms.md
| Referenced by | Scope |
|---------------|------|
| `SKILL.md` Route「Project」| whole file |
| `hub-norms.md` File index | whole file |
| `agent-check.md` § Covered content + § Domains | whole file |
| **Cites:** sibling `jeffrey-agent-workflow-skill/SKILL.md` § Projects (Governance files table + § Check list File language row) | § Projects |

### rule-norms.md
| Referenced by | Scope |
|---------------|------|
| `SKILL.md` Route「Rule」| whole file |
| `hub-norms.md` File index | whole file |
| `agent-check.md` § Covered content + § Domains | whole file |
| `content-boundaries.md` § Where agent-specific content lives + § Judging agent-specific content (placement pointer) | § Which home |

### memory-norms.md
| Referenced by | Scope |
|---------------|------|
| `SKILL.md` Route「Memory」| whole file |
| `hub-norms.md` File index | whole file |
| `agent-check.md` § Covered content + § Domains | whole file |
| `content-boundaries.md` § Decision tree | § Write |

### content-boundaries.md
| Referenced by | Scope |
|---------------|------|
| `SKILL.md` Route「Where recordable content goes / Rule vs Skill」| whole file |
| `hub-norms.md` File index | whole file |
| `rule-norms.md` header + § Which home | § Rule vs Skill triage / § Rule creation workflow |
| `project-norms.md` § Governance files | § Where agent-specific content lives |
| `preferences.md` § Naming & creation | § Rule vs Skill triage |
| sibling `jeffrey-agent-workflow-skill/SKILL.md` § Rules, Skills and repos + § Agent-specific spec index | § Rule vs Skill triage / § Judging agent-specific content |
| sibling `jeffrey-agent-workflow-skill/references/project-rules.md` (triage gate + templates table) + `delegate-new-chat.md` § Agent-specific procedure | § Rule vs Skill triage / § Where agent-specific content lives |
| sibling `jeffrey-agent-workflow-skill/README.md` / `README-EN.md` | whole file |
| **Cites:** `memory-norms.md` § Write; `rule-norms.md` § Which home; `skill-authoring.md` § File roles / § Positive / negative norms / § Agent-specific spec file; `preferences.md` header; sibling `jeffrey-agent-workflow-skill/references/project-rules.md` §1.1.1 + `SKILL.md` § Agent-specific spec index | pointer |

### preferences.md
| Referenced by | Scope |
|---------------|------|
| `SKILL.md` Route「preferences」+ Always | whole file |
| `hub-norms.md` File index + Must | whole file |
| `agent-check.md` § Depth + § Flow + § Cross-domain | whole file |
| `plugin-norms.md` / `project-norms.md` / `rule-norms.md` / `memory-norms.md` headers | whole file |

### sync-on-update.md
| Referenced by | Scope |
|---------------|------|
| `SKILL.md` Route「本轮被创建或修改」+ Always | whole file |
| `hub-norms.md` File index + Must | whole file |
| `skill-authoring.md` header | whole file |

### hub-norms.md
| Referenced by | Scope |
|---------------|------|
| `SKILL.md` Route「Norms/DoD」+ Always | whole file |

## scripts/

### run_agent_check.py
| Referenced by | Scope |
|---------------|------|
| `agent-check.md` § Flow + § Must | whole file (script-first gate) |
| `hub-norms.md` File index + § Must | whole file |
| `preferences.md` § Working style | whole file |
| `README.md` / `README-EN.md` 功能介绍 + 常见改动 | whole file |

## examples/

### three-layer-layout.md
| Referenced by | Scope |
|---------------|------|
| `SKILL.md` Layers table | whole file |
| `hub-norms.md` File index | whole file |
| `skill-authoring.md` § Thin hub / slash-attach budget (Reference layout line) | whole file |

### agent-snippet.md
| Referenced by | Scope |
|---------------|------|
| `hub-norms.md` File index | whole file |
| `skill-authoring.md` § Thin hub / slash-attach budget (Reference layout line) | whole file |
| **Cites:** `skill-authoring.md` § Prefer static / § Positive / negative norms; sibling `jeffrey-agent-workflow-skill/references/repo-exploration.md` | pointer |

## kind.txt
| Referenced by | Scope |
|---------------|------|
| `skill-authoring.md` § Skill kind + § File roles + § Synchronize companion files | whole file |
| `hub-norms.md` File index | whole file |
| `preferences.md` § Skill shape & language | whole file |