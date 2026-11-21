# DEVLOG

## 2026-11-22 01:03 +08
- 改了什么：跨 skill 复述清成指针。`references/content-boundaries.md` 决策树后新增「一类内容一个 skill」规矩（同样／同类内容不进两个 skill，其余 skill 只指针；相关 skill 会挂进对话故复述无意义；仅须脱离归属 skill 独立成立时才复述）。`references/preferences.md` 各节复述工作流／编写规范／枢纽规范的条目改指针，只留本页独有的偏好（建库先问、报告按内容讲、MCP 与插件锁卫生、UI 微文案）；`references/project-norms.md` 人类页与文件语言行改指工作流 § Projects。
- 为何：Jeffrey 2026-11-22：不同 skill 里不要有同样的内容和同类内容；非必要不复述；涉及对应 skill 的内容对话里会挂上该 skill。
- 涉及：`references/content-boundaries.md`、`references/preferences.md`、`references/project-norms.md`、`DEVLOG.md`。工作流侧同轮另记。

## 2026-11-22 01:25 +08
- 改了什么：`references/content-boundaries.md` 删 § Loading model（四种家加载方式表＋推论段）——加载机制只是讲给 Jeffrey 听的背景，不是规范条文；读法行同步删该节指针。「规则不只放记忆」的规范结论已由决策树事实/指令分流与 memory-norms 单一归属条承载，不丢。`references/hub-norms.md` 文件索引行、两份 README 功能条去掉「怎么加载」表述。
- 为何：Jeffrey 2026-11-22：「什么时候加载只是我想知道这个不用是规范」。
- 涉及：`references/content-boundaries.md`、`references/hub-norms.md`、两份 README、`DEVLOG.md`；无被引节丢失（cross-reference 各组未引用 § Loading model），关联记录不变。

## 2026-11-22 01:10 +08
- 改了什么：`references/content-boundaries.md` 吸收工作流程 skill `references/rule-vs-skill.md` 整文件（该仓已删）：新增 § Rule vs Skill triage（决策标准表、启发式、两条核心判断、写作规范指针、分类确认流程）、§ Rule creation workflow（A–F，原文重复的 E 编号顺手改为 E/F）、§ Where agent-specific content lives、§ Judging agent-specific content（五条归属测试＋共用判定＋试金石＋行动）；决策树与试金石段的跨文件指针改为内部节指针；外部指针补全限定（project-rules §1.1.1、skill-authoring 各节、rule-norms § Which home、工作流 SKILL.md § Agent-specific spec index）。`SKILL.md` 路由行意图扩（Rule vs Skill／创建规则／归属判断）、触发词补 创建规则／rule vs skill／规则还是技能／归属判断；`references/rule-norms.md` 头部与 § Which home 正典指针改本文件；`references/project-norms.md` 治理文件表存放指针改本文件；`references/preferences.md` 分类偏好指针改本文件；`references/cross-reference.md` 本文件组扩为完整被引/引用记录，skill-authoring 与 rule-norms 组的旧 sibling 引用行改名。
- 为何：Jeffrey 2026-11-22：「有边界文件就不需要 rule vs skill 了吧，都写到一起就好了」。
- 涉及：`references/content-boundaries.md`、`SKILL.md`、`references/rule-norms.md`、`references/project-norms.md`、`references/preferences.md`、`references/cross-reference.md`、`DEVLOG.md`；两份 README 功能条已述边界分派含分类与归属，无需再改。

## 2026-11-22 00:50 +08
- 改了什么：`references/content-boundaries.md` § Decision tree 试金石段后补一行指针：技能还是规则模糊时用工作流程 skill `references/rule-vs-skill.md` § Decision criteria 的两条核心判断（已有技能且条目多→就地迭代；能写成一步步执行步骤→技能，否则规则）。判据正文落在工作流程 skill（该仓另记），本处不复述。
- 为何：Jeffrey 审定边界草案时补充模糊情形的核心判据。
- 涉及：`references/content-boundaries.md`、`DEVLOG.md`；无文件/标题增删，cross-reference 不变。

## 2026-11-22 00:35 +08
- 改了什么：新增跨域分派器 `references/content-boundaries.md`：四种家（技能、用户级 AGENTS.md、项目规则、自动记忆——记忆与 Memory 是同一机制的两个作用域）的加载模型表（技能按描述触发挂载、用户级 AGENTS.md 每会话全文注入、项目规则进项目即注入、记忆只注入索引正文按需读），四步决策树（不持久→不记；事实→记忆用户级／项目级，决策语言事实归档案；指令→项目规则／用户级 AGENTS.md／应用专属归属／对应技能，先分类再确认；一句含事实＋指令→拆开各归其家），事实与指令的判别试金石（「我偏好X」是事实、「以后都要X」是指令），冲突优先级（项目内项目规则覆盖技能、技能规则压记忆复述、用户级 AGENTS.md 只管配置目录）。`SKILL.md` 路由表加行、frontmatter 触发词补 内容边界／记到哪／该写进哪个；`references/hub-norms.md` 文件索引加行；`references/cross-reference.md` 新增本文件组并给 memory-norms 组补被引行；两份 README 功能条各加一条。
- 为何：Jeffrey 2026-11-21：要在检查技能拟定记忆、AGENTS.md、SKILL、Memory 的边界——用户提出值得记录的内容时能依规则判定写成哪一个，定好给他看，并说明这几个东西 agent 怎么调用。
- 涉及：`references/content-boundaries.md`（新建）、`SKILL.md`、`references/hub-norms.md`、`references/cross-reference.md`、两份 README、`DEVLOG.md`。草案留本地待 Jeffrey 审。

## 2026-11-22 00:10 +08
- 改了什么：`references/memory-norms.md` § Write 就地补一条「单一归属、不重复记录」：一条事实的完整内容只存一个文件；Jeffrey 的决策倾向／语言体系事实归用户级档案 user-decision-language-profile，从其他条目吸收（搬移后删源条目或修剪成指针）；索引钩子与档案一行指针是导航不算第二份记录；行为规则归对应 skill。
- 为何：Jeffrey 2026-11-21 整理过往记忆进档案时明确「不要重复记录」。配套记忆整理（档案吸收工程选型标准整条、UI 插件兴趣条修剪重叠句）在用户级记忆侧执行。
- 涉及：`references/memory-norms.md`、`DEVLOG.md`；无文件/标题增删，cross-reference 不变；README 不列规范明细，无需改。

## 2026-11-22 00:02 +08
- 改了什么：`references/skill-authoring.md` § Agent-specific spec file 开头句纠正：分支集与命名从「agent 特定内容、由规格与项目规则承载」改「共用规则，以 `<agent>` 占位写在工作流程 skill § Git workflow」。
- 为何：Jeffrey 2026-11-22 纠正：分支机制可以不带 agent 名写成共用规则，不属特定内容；上一轮表述把它推去了特定内容。
- 涉及：`references/skill-authoring.md`、`DEVLOG.md`；无文件/标题增删，cross-reference 不变。本仓其他未提交改动原样保留、未随本次提交。

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