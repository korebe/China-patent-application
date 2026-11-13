# 调研方法、来源与复核口径

## 调研时间与范围

- 调研日期：2026-11-13。
- 范围：中国专利撰写、检索、技术交底、权利要求、审查意见及相关专利工作流。
- 重点：能否被 Codex 使用，以及安装、调用、依赖和实际适用边界。
- 星数：GitHub 页面在调研时显示的约数。星数随时间变化，只用来观察项目关注度，不作为质量、正确性或法律可信度评分。

## 如何判断 Codex 兼容性

| 标签 | 判定依据 |
|---|---|
| 明确支持 Codex | README、安装指南或配置文件明示 Codex |
| Codex 作者已验证 | 作者说明主要在 Codex 中运行或测试 |
| 可移植，待验证 | 使用通用 Agent Skills 文件结构，但作者没有明确声明 Codex 支持 |
| 未确认 | 安装指南主要面向其他工具，或实际 Skill 入口、依赖路径尚未确认 |
| 不是独立 Skill | 需要安装和启动完整桌面应用、后端或知识库服务 |

本次调研读取了各项目的公开 README、可访问的 `SKILL.md` 和安装说明；没有逐个在干净环境中安装、运行或比较生成质量。因此，目录中的兼容性表示“公开说明的证据”，不是“本地验收通过”。

## 星数与筛选说明

GitHub 页面显示的星数具有时效性，而且页面可能对高星项目使用约数。本目录记录的近似快照如下：

- 中国专利.skill：约 13.4k
- Paper2Patent：733
- CN Patent Drafting：8
- Patent Skills：0
- Evidence-First Patent Skill：0
- Patent Compose Skill：约 20
- Sati：约 3
- Patent Assistant 2026：约 15

查看最新星数请打开下方每个项目的 GitHub 页面。不要用星数替代以下判断：Skill 是否能被当前 Codex 版本发现、外部检索是否可信、法律依据是否更新、输出是否有材料支持。

## 项目来源

### 中国专利.skill

- [GitHub 项目页](https://github.com/handsomestWei/patent-disclosure-skill)
- [README](https://github.com/handsomestWei/patent-disclosure-skill/blob/main/README.md)
- [安装说明](https://github.com/handsomestWei/patent-disclosure-skill/blob/main/INSTALL.md)
- 阅读了 README 中的模块目录和安装说明。该安装指南主要说明 Claude Code 与 Cursor；Codex 兼容性因此标作待验证。

### Paper2Patent

- [GitHub 项目页](https://github.com/7toCR/paper2patent)
- [README](https://github.com/7toCR/paper2patent/blob/main/README.md)
- [主 Skill](https://github.com/7toCR/paper2patent/blob/main/skills/paper2patent/SKILL.md)
- README 明确列出 Codex，并说明作者主要在 Codex 中验证。

### CN Patent Drafting

- [GitHub 项目页](https://github.com/HuangXinzhe/cn-patent-drafting)
- [README 与安装说明](https://github.com/HuangXinzhe/cn-patent-drafting/blob/main/README.md)
- README 提供 Codex Desktop 插件、Skill Installer、手动安装和调用方式。

### Patent Skills

- [GitHub 项目页](https://github.com/yjmm10/patent-skills)
- [README](https://github.com/yjmm10/patent-skills/blob/master/README.md)
- [主 Skill](https://github.com/yjmm10/patent-skills/blob/master/SKILL.md)
- README 明确列出 Codex，目录含模式提示、参考文件和工具。

### Evidence-First Patent Skill

- [GitHub 项目页](https://github.com/soarsky1991/evidence-first-patent-skill)
- [README](https://github.com/soarsky1991/evidence-first-patent-skill/blob/main/README.md)
- [主 Skill](https://github.com/soarsky1991/evidence-first-patent-skill/blob/main/skill/draft-patents-evidence-first/SKILL.md)
- README 给出 Codex 安装路径和调用示例；主 Skill 覆盖证据标注、保密模式和阶段门。

### Patent Compose Skill

- [GitHub 项目页](https://github.com/yizchu/patent-compose-skill)
- [README](https://github.com/yizchu/patent-compose-skill/blob/main/README.md)
- README 说明 Skill 工作流和依赖；未发现 Codex 专门验证声明。

### Sati

- [GitHub 项目页](https://github.com/xujian519/sati)
- [README](https://github.com/xujian519/sati/blob/main/README.md)
- README 描述完整桌面应用、安装流程、工具和 Skill 目录，因此按应用而非单个 Codex Skill 收录。

### Patent Assistant 2026

- [GitHub 项目页](https://github.com/Mrliubai/patent-assistant-skill-2026)
- [README](https://github.com/Mrliubai/patent-assistant-skill-2026/blob/main/README.md)
- README 展示六阶段流程和 Claude Code 安装示例；没有明确 Codex 安装或验证说明，所以按参考项目收录。

## Codex 安装依据

- [OpenAI 官方 CLI Skill 安装说明](https://developers.openai.com/api/reference/cli)：当前项目使用 `.agents/skills/`，用户级安装使用 `~/.agents/skills/`。
- [OpenAI Skills 概念说明](https://developers.openai.com/plugins/concepts/skills)：说明 Skill 是包含指令和资源的目录。
- 第三方项目可能还沿用 `~/.codex/skills/`。遇到路径不一致时，先查当前 Codex 官方文档和本机技能发现状态，不要同时复制多个位置后假定安装成功。

## 如何从多家项目吸收思路

本目录做的是功能与流程对照，不是代码拼接。将来改进主专利 Skill 时，可以考虑按下表吸收经验证的做法：

| 可借鉴能力 | 主要参考 | 整合时的做法 |
|---|---|---|
| 技术事实与拟议设计分级 | Evidence-First | 为每个技术事实保留来源位置和状态；缺口明示，不补造 |
| 论文事实到权利要求依据的映射 | Paper2Patent | 建立逐项依据表，验证从属关系、术语、参数与附图引用 |
| 独立任务模式和阶段路由 | Patent Skills | 把初评、检索、交底、撰写、修改和导出拆成可单独调用的任务 |
| 多类型、多子技能工作流 | 中国专利.skill | 按发明、实用新型和外观分模板；逐个验证依赖和输出 |
| 工程材料到成套交付物 | CN Patent Drafting | 保留需求、文档包、质量清单和版本记录 |
| 项目分析和布局 | Patent Compose Skill | 参考阶段分解和中间文件，不照搬未经验证的自动检索结论 |
| 检索、OA、期限等专利工具设计 | Sati | 先验证数据来源、时效、权限和人工审批，再考虑集成 |
| 六阶段端到端检查单 | Patent Assistant 2026 | 只采纳可验证的流程检查点，不把项目说明当成能力证明 |

所有第三方代码都应按各自 LICENSE 使用。吸收工作流概念不代表复制代码、文字或模板；如需复用具体材料，应先检查许可并保留署名、版权和来源要求。

## 下一轮可复核项

- 在干净的 Codex 项目中逐个安装并验证能否发现 Skill。
- 记录安装后的 Codex 版本、系统平台、技能路径、依赖版本和测试用例。
- 用同一组脱敏样例比较材料提取、证据映射、权利要求结构、附图和 Word/PDF 输出。
- 检索功能单独记录数据源、查询日期、检索式和能否回到公开文本核验。
- 跟踪国家知识产权局法律、审查指南、电子申请系统及办事要求更新。
