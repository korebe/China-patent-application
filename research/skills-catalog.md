# 专利相关 Codex Skill 项目目录

调研日期：2026-11-13。GitHub 星数为当日显示的近似快照；项目代码、依赖、许可和安装方式可能随时间变化。这里记录作者公开材料中的功能，不代表我们已对每个项目做安装验收。

## 快速比较

| 项目 | GitHub 星数快照 | Codex 情况 | 更适合的任务 | 主要注意点 |
|---|---:|---|---|---|
| [中国专利.skill](https://github.com/handsomestWei/patent-disclosure-skill) | 约 13.4k | 通用 Agent Skills；作者安装说明未明确列 Codex，需试装 | 交底、申请文件、检索、解读、OA 辅助等模块化工作 | 依赖较多；高星不等于适用于 Codex |
| [Paper2Patent](https://github.com/7toCR/paper2patent) | 733 | 明确支持；作者称主要在 Codex 验证 | 论文转中国发明专利申请草稿、附图和 DOCX/PDF | 重点是“论文转专利”；不能代替查新与代理师判断 |
| [CN Patent Drafting](https://github.com/HuangXinzhe/cn-patent-drafting) | 8 | 明确支持 Codex | 研发材料到交底书、权利要求、说明书与文档包 | 星数低但 Codex 入口和材料交付路径清楚 |
| [Patent Skills](https://github.com/yjmm10/patent-skills) | 0 | README 明确支持 Codex | 评估、转写、查新、交底、迭代、DOCX、完整申请草稿 | 查新和 DOCX 有可选依赖；注意规则检索与版本核验 |
| [Evidence-First Patent Skill](https://github.com/soarsky1991/evidence-first-patent-skill) | 0 | README 给出 Codex 安装方式 | 证据清点、保密筛查、权利要求逐项溯源 | 强项是证据治理和披露准备，不主打最终申请文件 |
| [Patent Compose Skill](https://github.com/yizchu/patent-compose-skill) | 约 20 | 通用 Skill 目录；未明确验证 Codex | 项目分析、检索、专利布局、撰写与审查预演 | Python 3.10+ 和 Playwright；运行结果需核验 |
| [Sati](https://github.com/xujian519/sati) | 约 3 | 完整桌面专利代理系统，不是单个 Skill | 检索、文书、OA、期限费用等一体化工作台 | 安装体量大，Node 与本地服务配置较复杂 |
| [Patent Assistant 2026](https://github.com/Mrliubai/patent-assistant-skill-2026) | 约 15 | README 给出 Claude Code 安装；Codex 未验证 | 六阶段流程的参考思路：解析、检索、撰写、审查预测、答复 | 先核对仓库中的实际 Skill 文件和可执行入口 |

## 1. Paper2Patent

**项目地址：** [7toCR/paper2patent](https://github.com/7toCR/paper2patent)  
**定位：** 把论文、学位论文或技术材料整理成中国发明专利申请草稿，附带附图、检查器和撰写说明。项目 README 明确写明 Codex 支持，并称作者主要在 Codex 中验证。

**适合什么时候用**

- 输入主体是一篇论文或科研成果，目标是形成一份可交代理师审核的发明专利初稿。
- 需要把论文事实、权利要求、说明书、附图和待补信息分开管理。
- 需要自动检查摘要长度、权利要求引用、附图标记等形式问题。

**安装与调用**

1. 克隆项目。
2. 将仓库中的 `skills/paper2patent` 整个目录复制到当前项目的 `.agents/skills/paper2patent/`，或用户目录的 `~/.agents/skills/paper2patent/`。
3. 新开 Codex 会话，检查技能是否出现。
4. 调用示例：`$paper2patent 请基于这篇论文先梳理发明点和权利要求布局，标出公开风险和待补材料；等我确认后再生成申请文件草稿。`

项目 README 写有 Python 3.9+；绘图需要 Pillow 和中文字体，导出 PDF 需要 LibreOffice。其安装说明使用旧版 `~/.codex/skills` 示例，Codex 新版路径按本目录首页的官方路径提示处理。

**优点**

- README 和 Skill 文件都把“论文依据”“不得补造内容”“公开状态核查”写得具体。
- 生成申请文件、撰写说明、支持关系和附图的流程完整。
- 作者明确报告在 Codex 里验证，兼容性证据较强。

**限制**

- 以论文转专利为中心；非论文型工程项目可考虑 CN Patent Drafting 或 Evidence-First。
- 论文已经公开时，是否仍可申请高度依赖公开时间、公开方式和适用法律，不应让模型单独给结论。
- 自动检查只能发现部分形式问题，不能证明新颖性、创造性、充分公开或权利稳定性。

## 2. CN Patent Drafting

**项目地址：** [HuangXinzhe/cn-patent-drafting](https://github.com/HuangXinzhe/cn-patent-drafting)  
**定位：** 明确面向 Codex 的中国发明专利撰写 Skill。README 提供 Codex Desktop 插件市场、Skill Installer 和手动安装说明。

**适合什么时候用**

- 输入包含代码、设计文件、实验记录或零散研发说明，而不是一篇完整论文。
- 需要从技术点一直做到权利要求书、说明书、摘要和申请文档包。
- 需要在已有草稿上合并材料、修正并保留版本记录。

**安装与调用**

1. 优先按仓库 README 将其插件市场加入 Codex Desktop，或把仓库根目录 Skill 安装到 `.agents/skills/cn-patent-drafting/`。
2. 保留整个目录，尤其是 `references/`、`scripts/` 和 `SKILL.md`。
3. 新开会话后调用：`$cn-patent-drafting 请先从这些研发材料提取候选发明点，逐项列出证据位置和缺失信息，先不要写最终权利要求。`

核心功能据 README 不需要额外依赖；仓库脚本使用 Python 标准库。

**优点**

- Codex 支持说明明确，Windows 插件安装也有专门说明。
- 支持材料盘点、交底、检索辅助、申请文件和支持性检查。
- 可以把它作为非论文型案件的主 Skill。

**限制**

- 星数较低，公开项目的受众和使用量有限，星数不能替代本地试用。
- 仍需逐项检查其法律规范版本、检索来源和输出模板是否适合具体申请人或代理机构。

## 3. Patent Skills

**项目地址：** [yjmm10/patent-skills](https://github.com/yjmm10/patent-skills)  
**定位：** README 明确列出 Codex，并提供根目录 Skill。按模式组织：可专利性初评、论文或技术说明转专利、查新、交底撰写与迭代、A4 导出和申请书草稿。

**安装与调用**

1. 将仓库根目录整体安装到 `.agents/skills/patent-skills/`，不能只复制 `SKILL.md`，因为模式指令、参考文件和工具都在子目录中。
2. 重新打开 Codex 会话。
3. 调用示例：`$patent-skills 先做规范核验和技术材料盘点，再查新、形成差异点表；每一步先给我确认，暂不生成最终申请书。`

可选依赖包括 DOCX 导出依赖，以及用于国知局检索的 Playwright/Chromium。README 表示没有这些依赖时会降级，但要确认实际检索来源和结果是否可用。

**优点**

- 把全流程拆成可单独调用的模式，不必每次从头跑完整流程。
- 对迭代留痕、模板选择和规范查询有明确路由。
- Codex 配置文件和目录结构都在仓库中。

**限制**

- 星数尚未形成社区验证信号。
- 联网核验的输出仍需记录官方来源、访问日期和适用版本；不能只接受生成的结论。

## 4. Evidence-First Patent Skill

**项目地址：** [soarsky1991/evidence-first-patent-skill](https://github.com/soarsky1991/evidence-first-patent-skill)  
**定位：** 将会议纪要、图纸、实验记录和公开资料整理成有来源、有状态的证据账本，再为交底书和权利要求框架提供依据。README 给出 Codex 安装命令。

**安装与调用**

1. 将 `skill/draft-patents-evidence-first` 子目录复制到 `.agents/skills/draft-patents-evidence-first/`。
2. 按 Skill 中的流程初始化案件目录，再做敏感信息扫描。
3. 调用示例：`$draft-patents-evidence-first 先做材料清单和保密扫描，把每项内容标成实测、已有记载、推断或拟议设计；未经我确认，不要联网检索或开始实质撰写。`

项目要求 Python 3.11 或兼容版本。README 说明初始化、校验和敏感信息扫描不需要安装依赖；是否使用外部检索取决于明确的保密模式和人工批准。

**优点**

- 把“已有事实、推断、拟议设计、待验证目标”分开，降低模型把目标写成已实现效果的风险。
- 权利要求的每项限定都要能回溯到来源，适合多人研发团队和敏感项目。
- 有明确的人工作为选题、披露和外部检索闸门。

**限制**

- 重点是证据治理和交底准备，不是自动完成正式提交。
- 工作流较严谨，启动和维护案件数据结构需要时间。
- 不应把它的证据标签直接写成对外申请文件的法律结论。

## 5. 中国专利.skill

**项目地址：** [handsomestWei/patent-disclosure-skill](https://github.com/handsomestWei/patent-disclosure-skill)  
**定位：** 本次调研中星数最高的专利相关项目。README 展示多个子 Skill：交底、申请文件、交底到申请编排、专利解读、专利地图、审查意见辅助、著录检索和政策简报。

**Codex 兼容状态**

仓库按 Agent Skills 常见格式组织，根目录有 `SKILL.md`，所以结构上有可移植性；但作者的安装文档明确写的是 Claude Code 和 Cursor，没有明确承诺 Codex。应标为“可移植，待验证”，先在隔离测试项目中检查技能发现、依赖运行和输出。

**安装与调用**

1. 若试用 Codex，把完整仓库复制到 `.agents/skills/patent-disclosure-skill/`，保留根级 Skill 以及 `skills/` 子目录。
2. 先检查根级 Skill 如何路由到子 Skill，并按该仓库的 `INSTALL.md` 安装 Python、浏览器和其他依赖。
3. 试用提示：`请先阅读 patent-disclosure-skill 的入口规则。基于我提供的技术资料，只完成发明交底书的信息盘点和缺口问题清单，告诉我需要哪些依赖和会生成哪些文件，暂不提交或公开任何材料。`

默认交底流程依赖 Python 3.9+，包含 Playwright / Chrome 或 Edge 等环境；检索、图表、图像和其他子 Skill 可能还需要额外组件。逐个功能验收，不能因为仓库被发现就假定全部子功能可运行。

**优点**

- 星数和模块覆盖度突出，适合作为流程设计和能力覆盖的参考。
- 覆盖发明、实用新型、外观设计及后续解读、检索和答复辅助。
- 有多类输入、多个产物和迭代场景的说明。

**限制**

- 高星反映关注度，不代表 Codex 兼容性、法律正确性或输出质量。
- 模块和依赖很多，初次安装与排障成本高。
- OA 答复及政策分析需要按官方案卷、法律条文和审查指南逐项核对。

## 6. Patent Compose Skill

**项目地址：** [yizchu/patent-compose-skill](https://github.com/yizchu/patent-compose-skill)  
**定位：** 以项目文件分析、查新、交底书、权利要求和后续审查预演构成工作流。README 允许支持 Skill 的编码助手使用，但没有明确说明已在 Codex 中测试。

**安装与调用**

1. 先在临时项目试用；如需安装，保留完整 Skill、提示词、脚本和依赖目录，放入 `.agents/skills/patent-compose-skill/`。
2. 按 README 安装 Python 3.10+ 及 `requirements.txt` 中的依赖；部分检索能力需要 Playwright/Chromium。
3. 调用示例：`请使用 patent-compose-skill 分析当前项目，先列出技术模块和候选专利点，再生成检索计划；每个阶段结束时停下来让我审核。`

**优点**

- 把项目扫描、专利布局、查新和撰写连在一起。
- 输出结构和中间材料较丰富，适合借鉴阶段拆分和权利要求树的组织方式。

**限制**

- Codex 支持未由项目明确验证，应测试文件读取边界、命令权限和生成路径。
- 外部检索、浏览器和较多 Python 依赖增加运行故障面。
- 多阶段自动化不能替代人工确认每个发明点是否真实、可披露。

## 7. Sati

**项目地址：** [xujian519/sati](https://github.com/xujian519/sati)  
**定位：** 面向专利从业者的桌面端专利智能体，包含 Skill、检索和工作流工具、知识库与本地服务。它是完整应用，不是可以通过复制一个 `SKILL.md` 就安装的 Codex Skill。

**适合什么时候用**

- 需要单独评估一个专利专用工作台，涉及检索、文书、OA、权利要求对照、案件期限或费用。
- 有条件按项目要求配置 Node、依赖、数据库或本地服务，并做独立安全评估。

**试用方式**

从其 README 的 Windows 或 macOS/Linux 安装说明开始，按官方步骤安装并启动本地服务；先使用公开样例，确认模型配置、检索来源、数据落盘位置和外部联网行为，再考虑真实案件。不要把完整应用安装说明简化成“把 Sati 当 Skill 复制进 Codex”。

**优点**

- 专利业务覆盖和工程化程度较广，适合研究专业工作流如何拆分工具、检查点和人工审批。
- 可以为本仓库未来设计检索、期限、费用、OA 等模块提供参考。

**限制**

- 安装和运行成本明显高于单一 Skill。
- README 中的工具数量和知识库规模是项目自述，随版本变化，不能当成独立质量验证。
- 本目录没有验证其服务与 Codex 的直接集成。

## 8. Patent Assistant 2026

**项目地址：** [Mrliubai/patent-assistant-skill-2026](https://github.com/Mrliubai/patent-assistant-skill-2026)  
**定位：** README 描述六阶段流程：技术解析、查新、可专利性分析、申请文件、审查预测和答复。

**Codex 兼容状态**

README 的安装示例是复制到 Claude Code 的 `~/.claude/skills/`，没有明确给出 Codex 安装方式。将其作为流程参考；只有确认仓库存在有效的 Skill 入口、依赖路径可用并在 Codex 实测后，才标记为可安装。

**使用分析**

可以从 README 了解它如何拆解任务，例如：先解析技术方案，再检索和比对，然后撰写申请草稿，最后模拟审查意见。不要按“全流程代理、从查新到授权”这类宣传文案推断它可以正式递交申请或保证授权。

**优点**

- 六个阶段划分直观，适合作为工作流检查清单的参考。
- 申请前后流程都有提及。

**限制**

- Codex 支持未确认；目前更适合作为阶段设计参考，而不是 Codex 主 Skill。
- 星数低，且星数无法验证其检索覆盖、法律结论或答复质量。
