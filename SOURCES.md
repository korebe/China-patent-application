# 参考项目

本技能根据下列 GitHub 项目公开展示的流程和能力设计。我们借鉴的是工作流思路，没有复制其代码或整段提示词。

星数记录于 2026-11-13，只表示项目在 GitHub 上受到关注，不代表法律准确性或输出质量。

## 主要参考

| 项目 | 借鉴的做法 |
|---|---|
| [handsomestWei/patent-disclosure-skill](https://github.com/handsomestWei/patent-disclosure-skill)（约 13.4k 星） | 将交底、申请文件、检索、案卷和审查答复拆成不同任务入口。 |
| [7toCR/paper2patent](https://github.com/7toCR/paper2patent)（约 733 星） | 论文转申请文件时保留来源、生成附图，并检查 Word/PDF 产物。项目说明主要在 Codex 中验证。 |
| [HuangXinzhe/cn-patent-drafting](https://github.com/HuangXinzhe/cn-patent-drafting)（约 8 星） | 准备申请材料包、请求书信息表、提交清单和权利要求支持检查。 |
| [soarsky1991/evidence-first-patent-skill](https://github.com/soarsky1991/evidence-first-patent-skill) | 记录每项技术事实的来源，区分实测、记载、推断和设想。 |
| [yjmm10/patent-skills](https://github.com/yjmm10/patent-skills) | 组织交底书、申请文件、规范核对和版本迭代。 |
| [yizchu/patent-compose-skill](https://github.com/yizchu/patent-compose-skill) | 规划申请组合和权利要求层次，预演审查意见。 |
| [xujian519/sati](https://github.com/xujian519/sati) | 记录案卷阶段、期限、费用和人工确认点。它是桌面应用，不是单独的 SKILL.md。 |
| [Mrliubai/patent-assistant-skill-2026](https://github.com/Mrliubai/patent-assistant-skill-2026) | 将检索、申请文件、审查预测和答复拆成多个阶段。 |

## 本技能的组合方式

- 用分阶段入口控制流程，避免一次生成整套申请而跳过事实确认。
- 用证据台账把技术材料连到权利要求和附图。
- 用官方来源核对现行规则、通知和费用，不依赖旧模板中的固定数字。
- 把提交、审查答复和授权后维护放入案卷流程。
- 需要第三方代码、模板或原文时，先单独核对该项目当前许可证和署名要求。
