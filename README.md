# China Patent Application Skill for Codex

整合中国发明、实用新型和外观设计申请的 Codex 工作流。技能以证据和官方来源为准，覆盖申请准备、文件起草、官方提交准备、审查意见协助和授权后案卷维护。

## 安装到 Codex

把整个仓库克隆到 Codex 可发现的个人 skill 目录，或放入当前项目的 .agents/skills/ 下。Windows PowerShell 示例：

~~~powershell
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.agents\skills"
git clone https://github.com/korebe/China-patent-application.git "$env:USERPROFILE\.agents\skills\china-patent-application"
~~~

也可以在项目内使用：

~~~powershell
New-Item -ItemType Directory -Force -Path ".agents\skills"
git clone https://github.com/korebe/China-patent-application.git ".agents\skills\china-patent-application"
~~~

开始新的 Codex 会话后，可以直接说“使用 china-patent-application，先盘点这批研发材料并找出需要我确认的事实”。Codex 的 skill 以 SKILL.md 为入口，可按需读取参考文件和模板。

## 工作范围

- 技术材料盘点、保密边界和证据台账
- 发明点梳理、查新、现有技术对比及申请类型选择
- 交底书、权利要求、说明书、摘要、附图和提交清单
- 权利要求支持性、附图标记、术语及材料一致性检查
- 审查意见拆解、对比文件映射和答复草稿
- 案卷、官方通知、程序期限、缴费和授权后年费的记录与复核

正式递交、缴费、签署和其他法律手续应由申请人或受托专业人员在国家知识产权局官方系统办理。本技能不自动提交申请或付款，也不替代专利代理师或律师的判断。

## 文件结构

- SKILL.md：阶段路由和通用决策门
- references/：阶段细则及官方来源入口
- templates/： intake、证据、检索、审查意见和案卷模板
- SOURCES.md：参考项目和本技能的整合方式

本项目不会自动把你的案件材料写入 Git。请将案件工作区和该 skill 仓库分开。
