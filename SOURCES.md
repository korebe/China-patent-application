# 项目来源与整合说明

本仓库是面向 Codex 的原创工作流整合。下列项目用于比较公开能力、流程设计和护栏；本仓库未将其代码或大段指令直接拼接进来。使用第三方脚本、模板或文本时，应单独核对对应仓库当前许可证、署名和分发条件。

星数记录于 2026-11-13，仅用于衡量 GitHub 关注度，不代表法律准确性或输出质量。

## 主要参考

| 项目 | 本次参考的能力 |
|---|---|
| [handsomestWei/patent-disclosure-skill](https://github.com/handsomestWei/patent-disclosure-skill) | 中国专利场景的模块化路由：交底、申请文件、检索、案卷、审查答复和专利解读；GitHub 页面约 13.4k stars。 |
| [7toCR/paper2patent](https://github.com/7toCR/paper2patent) | 明确面向 Codex 的论文转专利流程、来源忠实、附图生成、Word/PDF 输出和交付前自动检查；约 733 stars。 |
| [HuangXinzhe/cn-patent-drafting](https://github.com/HuangXinzhe/cn-patent-drafting) | Codex 原生申请材料包、请求书信息确认表、提交清单、权利要求支持映射和修订记录；约 8 stars。 |
| [soarsky1991/evidence-first-patent-skill](https://github.com/soarsky1991/evidence-first-patent-skill) | 证据分级、来源定位、逐项权利要求溯源、保密扫描和人工选题门。 |
| [yjmm10/patent-skills](https://github.com/yjmm10/patent-skills) | 交底书到申请文件的阶段组织、规范更新核查、迭代留痕和 Word 交付。 |
| [yizchu/patent-compose-skill](https://github.com/yizchu/patent-compose-skill) | 申请组合布局、权利要求层级规划和审查答复预演。 |
| [xujian519/sati](https://github.com/xujian519/sati) | 多阶段案卷状态、期限/费用/法律状态查询、人工确认点和专业角色复核。它是完整桌面智能体项目，不是仅复制一个 skill 即能使用的工具。 |
| [Mrliubai/patent-assistant-skill-2026](https://github.com/Mrliubai/patent-assistant-skill-2026) | 技术理解、检索、可专利性分析、审查预测和答复策略的阶段拆解；其仓库安装结构需使用前另行核验。 |

## 整合选择

- 以中国专利技能的分阶段路由作为入口，避免把交底、申请、检索和 OA 答复混成一个无分支长提示。
- 以证据台账和权利要求—说明书—附图映射作为质量主线。
- 把论文/代码转换与普通技术材料分开处理，保留源文件位置、公开时间和证据状态。
- 把正式提交前的文件检查、官方事务后的案卷记录、答复期限和授权后维护纳入生命周期。
- 所有程序、费用和审查规则均从国家知识产权局现行官方页面核实，不把旧技能内的静态数字当作当前规则。

主要仓库许可证各不相同；引用项目的存在不表示其代码、提示词或材料可直接复制。此整合未 vendoring 第三方代码。
