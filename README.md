# 中国专利申请：Codex Skill

这个仓库提供一套用于中国发明、实用新型和外观设计专利的 Codex 工作流，覆盖从技术材料整理到申请后案件记录。

## 安装

将整个仓库放入 Codex 的个人技能目录，或当前项目的 .agents/skills/ 目录。

Windows PowerShell：

~~~powershell
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.agents\skills"
git clone https://github.com/korebe/China-patent-application.git "$env:USERPROFILE\.agents\skills\china-patent-application"
~~~

项目内安装：

~~~powershell
New-Item -ItemType Directory -Force -Path ".agents\skills"
git clone https://github.com/korebe/China-patent-application.git ".agents\skills\china-patent-application"
~~~

私人仓库需要 GitHub 登录权限。安装后开启新的 Codex 会话。

## 使用

可以直接说：

~~~text
使用 china-patent-application，先阅读这批研发材料，列出候选专利点和需要我确认的问题。不要开始写申请文件。
~~~

也可以明确指定阶段，例如“查新这项技术”“把已确认的交底书整理成申请文件”或“分析这份审查意见通知书”。

## 工作阶段

1. 收集技术材料并检查保密要求。
2. 找出候选专利点，确认技术事实和公开时间。
3. 检索现有技术，逐项比较相同点和区别。
4. 起草交底书、权利要求、说明书、摘要和附图。
5. 检查权利要求是否有说明书依据，核对图号、术语和申请信息。
6. 准备官方提交清单；申请人或代理师确认后自行递交。
7. 记录通知书、答复、授权登记、费用和年费事项。

## 重要边界

技能提供工作底稿和案件管理辅助。它不会登录国知局、正式递交申请、签署文件或支付费用。申请人或专利代理师应核对最终文本、法律判断、程序期限和官方手续。

参考项目与本技能如何整合，见 SOURCES.md。现行法律、审查指南和系统入口见 references/06-authoritative-sources.md。
