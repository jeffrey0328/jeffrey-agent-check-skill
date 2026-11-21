# DEVLOG

## 2026-11-21 23:58 +08
- 改了什么：`references/skill-authoring.md` § Agent-specific spec file 原地迭代：删去指向工作流程 skill 已删 `references/agent-branches.md` 的悬空指针，分支集与命名改「属 agent 特定内容，由该代理的规格与项目自身规则承载」；本节 `<agent>/main` 字面全改通用「基分支」表述；索引行规范改「命名规则＋存放位置（当前代理基分支）」；新增一条规则：专属 spec 文件不写自己在哪个分支，存放位置只由索引行承载。
- 为何：Jeffrey 2026-11-21：工作流程 skill 收敛删除 agent-branches.md 后指针悬空；补充指示「agent 专属内容的文件不需要写文件在哪个分支」，按规范落进本节。
- 涉及：`references/skill-authoring.md`、`DEVLOG.md`；无文件/标题增删，cross-reference 不变。本仓其他未提交改动（memory-norms、preferences 及 DEVLOG 既有未提交条目）原样保留、未随本次提交；hub-norms／rule-norms／sync-on-update 里的 `<agent>/main` 字面本次未动。

## 2026-11-21 23:55 +08
- 改了什么：`references/preferences.md` § Working style 就地补两条偏好：提问卡自带上下文（主题＋一句背景＋问题，冷读卡）、已答过的不再问、开放决策合并一轮卡片（指针到工作流程 skill § Asking Jeffrey）；对话出现新信号时自动维护用户级记忆里的决策倾向／语言体系档案 user-decision-language-profile（指针到工作流程 skill § Memory updates）。
- 为何：Jeffrey 2026-11-21：「通过记忆记住我的决策倾向、语言体系，每次检测到有可更新的就要更新进去，沟通要高效不要一个问题让我反复重复」。操作规则正文写进工作流程 skill（该仓另记），本页按 § Adding a preference 收录偏好。
- 涉及：`references/preferences.md`、`DEVLOG.md`；无文件/标题增删，cross-reference 不变；README 只述枢纽职责不列偏好明细，无需改。

## 2026-11-21 23:20 +08
- 改了什么：自动挂载由「常驻」改为「相关内容触发」。frontmatter description 重写：对话创建、修改、审阅或使用任何 agent 相关内容（skill、插件含 customize、MCP 服务器与配置、记忆、项目规则 AGENTS.md/.agents//.mdc、应用规格）时即加载，先检查再动手，挂载后整条对话生效；触发词表补 改skill／编辑skill／写skill／plugin／customize／MCP／AGENTS.md／memory／记忆／写记忆／改记忆。`SKILL.md` Always 首条「Resident + mandatory gate」改「Content-triggered + mandatory gate」；`references/hub-norms.md` 常驻条、`references/sync-on-update.md` 开头常驻声明、`references/skill-authoring.md` § Auto-invocation decision 当前模式表（本 skill 改「条件自动 / 相关内容触发」并记实测依据）、两份 README 怎么用首行与功能条（常驻同步→配套同步）同步。
- 为何：Jeffrey 2026-11-21：一整轮编辑 skill／记忆／插件／AGENTS.md 的对话里本 skill 从未自动挂载；先按祈使式常驻重写 description，新对话实测仍不挂——测试对话自述看到了新描述、知道「按规则应首轮加载」但仍未加载，证明常驻式被模型当可选噪声。Jeffrey 定调：不应常驻触发，应通过相关内容触发。
- 涉及：`SKILL.md`（frontmatter＋Always）、`references/hub-norms.md`、`references/sync-on-update.md`、`references/skill-authoring.md`、`references/rule-norms.md`、两份 README、`DEVLOG.md`；无文件/标题增删（§ Resident 标题语义为「挂载期间的常设职责」，保留），cross-reference 不变。另按 Jeffrey 同日在另一对话定下的分支命名（`agent/<agent>`→`<agent>/main`，见工作流程 skill `references/agent-branches.md`）就地更新本 skill 承载的命名规则：skill-authoring § Agent-specific spec file 三处、rule-norms § Which home／Check list／Must／Must not 四处、sync-on-update 更新时检查条一处、hub-norms 三处。改完另开新对话复测内容触发。

## 2026-11-21 14:30 +08
- 改了什么：新增 skill 必备配套「全中文更新日志」规范。`references/skill-authoring.md`：§ File roles 加 `DEVLOG.md` 行；新增 § Update log（根目录、全中文、最新在前、每条 改了什么/为何/涉及、每次实质更新一条、缺失或非中文两档均 must-fix、旧外文条目就地翻译）；§ Language 表加 `DEVLOG.md` 中文行；§ Synchronize companion files、§ Post-write user brief、§ Prefer static 同步。`references/hub-norms.md`：File index 加行、Human entry 段、配套必备条、语言条、DoD 同步。`references/agent-check.md` Quick 档语言口径与 § Flow 脚本描述同步。`references/preferences.md` skill 形态语言条同步。`references/sync-on-update.md` 配套表加 `DEVLOG.md` 行。`scripts/run_agent_check.py`：`check_skill` 加 DEVLOG 存在与中文检查，英文语言循环豁免 `DEVLOG.md`。本 skill 补建本文件；`jeffrey-agent-config-skill`、`jeffrey-repo-sync-skill` 补建种子日志；`jeffrey-agent-workflow-skill` 英文日志就地转中文并补记当日更新。
- 为何：Jeffrey 2026-11-21：skill 除了中文 README.md 其余全英文（README 中英对仍强制必备，经卡片确认维持现状），并再加一个全中文的更新日志。
- 涉及：`references/skill-authoring.md`、`references/hub-norms.md`、`references/agent-check.md`、`references/preferences.md`、`references/sync-on-update.md`、`references/cross-reference.md`、`scripts/run_agent_check.py`、两份 README、`DEVLOG.md`（新建）；舰队其余 skill 的 DEVLOG 补齐与检查另记。