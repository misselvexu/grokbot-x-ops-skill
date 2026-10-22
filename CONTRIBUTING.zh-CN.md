# 参与贡献

[English](CONTRIBUTING.md) | **简体中文**

感谢你帮助改进本项目。参与即表示你同意遵守我们的[行为准则](CODE_OF_CONDUCT.md)。

## 贡献方式

- **报告问题**——skill 中某一步执行失败、表述不清，或已与产品不符。请使用 [Bug 报告表单](https://github.com/misselvexu/grokbot-x-ops-skill/issues/new?template=bug_report.yml)。
- **提出改进**——新的护栏、更好的 routine、平台迁移方案等。请使用[功能建议表单](https://github.com/misselvexu/grokbot-x-ops-skill/issues/new?template=feature_request.yml)。
- **改进文档或翻译**——欢迎任何让表述更清晰、翻译更准确的修改。
- **提交 Pull Request**——见下方说明。

## 基本规则

1. **必须中英同步。** 对 skill 或文档的任何修改，都要同时更新英文和简体中文。`SKILL.md` 的每一节先英文、后中文，两者描述的步骤必须一致。
2. **不编造。** 关于 X、Grok Bot 或平台规则的每条事实陈述，都要附上公开来源链接；推断要明确标注为推断。
3. **安全优先。** 修改不得削弱默认护栏：默认人工审批、Bot 不接触凭据、低频、自动风控刹车。提高自动化程度的提议必须说明风险，并保持为可选项。
4. **不含隐私数据。** 不要包含真实账号（`@<handle>` 这类占位符除外）、个人信息、API key、token、Cookie 或私人账号截图。
5. **占位符保持通用。** 使用 `<workdir>`、`<tz>`、`<handle>` 等占位符，不写真实值。

## Pull Request 流程

1. Fork 本仓库并新建分支：`git checkout -b docs/clarify-step-5`。
2. 用两种语言完成修改。
3. 在 `CHANGELOG.md` 的 `[Unreleased]` 下记录变更。
4. 提交 Pull Request，并完成模板中的检查清单。
5. 维护者会进行审阅。小而聚焦的 PR 审阅最快。

## 写作风格

- 英文：平实、直接，说明性步骤用祈使句（"Ask the owner…"、"Do not…"）。
- 中文：简洁的简体中文；skill、routine、Test run、Connect apps 等产品术语保持与产品界面一致。
- Markdown：每个要点尽量一句话；结构化对比用表格。

## 安全问题

请勿在公开 Issue 中报告安全问题，详见 [SECURITY.md](SECURITY.md)。
