# 相关专利 Skill 调研

> 这组资料用于在 Codex 中选用、安装和组合中国专利相关 Skill。它记录第三方项目的能力与限制，不复制第三方代码。

## 先看这里

- 想从论文生成中国发明专利申请草稿：先看 [Paper2Patent](./skills-catalog.md#1-paper2patent)。
- 想处理研发材料、权利要求和成套申请文档：看 [CN Patent Drafting](./skills-catalog.md#2-cn-patent-drafting)。
- 想先把证据、事实和推断分清，再决定是否撰写：看 [Evidence-First Patent Skill](./skills-catalog.md#4-evidence-first-patent-skill)。
- 想了解覆盖面大、星数高的模块化项目：看 [中国专利.skill](./skills-catalog.md#5-中国专利skill)；Codex 兼容性需先在自己的环境验证。
- 需要完整桌面专利工作台，而不只是 Codex Skill：看 [Sati](./skills-catalog.md#7-sati)。

然后按 [组合与使用流程](./workflow-and-usage.md) 选一个主 Skill，再将其他项目作为补充审阅参考。

## 文件导航

| 文件 | 回答的问题 |
|---|---|
| [skills-catalog.md](./skills-catalog.md) | 每个项目做什么、Codex 兼容情况、如何安装与调用、优点和限制 |
| [workflow-and-usage.md](./workflow-and-usage.md) | 专利工作各阶段适合参考谁，怎样在 Codex 中组合使用 |
| [assessment-method.md](./assessment-method.md) | 星数、来源、兼容性标签和筛选方法 |

## 兼容性标签

- **明确支持 Codex**：项目说明或 Codex 配置明确列出 Codex。
- **Codex 作者已验证**：项目明确说明主要在 Codex 中验证。
- **可移植，待验证**：文件采用通用 Agent Skills 结构，但作者没有明确承诺 Codex 支持。
- **不是独立 Skill**：项目是桌面应用或完整代理系统；不能只复制一个 SKILL.md 就视为装好了。

标签描述的是项目公开说明，不代表我们已在本机完整安装、运行或验证其输出质量。

## Codex 安装路径提示

截至 2026-11-13，OpenAI 官方安装说明列出的 Codex 路径是：

- 当前项目：`.agents/skills/<skill-name>/`
- 当前用户的所有项目：`~/.agents/skills/<skill-name>/`

请把 Skill 的整个目录复制进去，确保其中有 `SKILL.md` 及其引用的 `references/`、`scripts/` 等文件；然后新开 Codex 会话并检查是否能发现技能。部分第三方 README 仍写 `~/.codex/skills/`，安装前请以你的 Codex 版本和官方说明为准。Codex Desktop 插件市场安装方式只适用于项目明确提供插件包的情况。

官方说明：[OpenAI Codex Skill 安装指南](https://developers.openai.com/api/reference/cli)

## 选择原则

1. 先明确任务：交底书、论文转申请、检索、审查意见答复，还是工作台管理。
2. 每个案件选一个主 Skill，负责材料、版本和最终草稿。
3. 其他 Skill 只做指定的独立检查，例如证据溯源、权利要求支持性或格式检查。
4. 检索结果、法条、审查指南版本和官方平台事项都要回到官方来源核验。
5. 任何生成草稿都先由申请人确认技术事实和披露边界，再交专利代理师审核；Skill 不能替代代理师，也不自动完成正式提交。

详细对照、提示词和阶段分工见 [组合与使用流程](./workflow-and-usage.md)。

## 范围

本目录只收录与中国专利撰写、检索、审查或证据管理直接相关的公开项目。星数是调研时的快照，会变化；星数只反映 GitHub 关注度，不是准确率、法律质量或授权率排名。所有项目按其原始许可使用，引用时保留来源，不在本仓库镜像其代码。
