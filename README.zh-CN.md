<div align="center">

# Grok Bot X 运营 Skill

**一条消息，把你的 Grok Bot 变成一支由你把关的 X 账号“小编辑部”。**

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)](CHANGELOG.md)
[![Language](https://img.shields.io/badge/language-EN%20%7C%20%E4%B8%AD%E6%96%87-orange.svg)](README.md)
[![Skill](https://img.shields.io/badge/skill-x--ops--team--setup-6f42c1.svg)](skills/x-ops-team-setup/SKILL.md)

[English](README.md) | **简体中文**

![封面](assets/cover.jpg)

</div>

## 目录

- [项目简介](#项目简介)
- [快速开始（一键复刻）](#快速开始一键复刻)
- [会搭建什么](#会搭建什么)
- [架构](#架构)
- [安全与护栏](#安全与护栏)
- [方法论要点](#方法论要点)
- [文档](#文档)
- [常见问题](#常见问题)
- [路线图](#路线图)
- [参与贡献](#参与贡献)
- [许可证](#许可证)
- [免责声明](#免责声明)

## 项目简介

`x-ops-team-setup` 是一个独立、完整、中英双语的 [Grok Bot](https://docs.x.ai/grok-bot/bots) skill 文件。把它交给你的主 Bot，它会先和你做一次简短的设置问答，然后搭好一整套 X（Twitter）运营组：专职 Bot、可复用 skill、定时 routines，以及“草稿 → 审批 → 发布”的工作流。

设计原则很简单：**自动化的是准备，不是判断。** Bot 按时研究、核实、起草和复盘，发什么由你决定。

## 快速开始（一键复刻）

把下面这句话发给你的主 Grok Bot：

```text
读取 https://raw.githubusercontent.com/misselvexu/grokbot-x-ops-skill/main/skills/x-ops-team-setup/SKILL.md ，把它存成 skill，然后和我一起运行它。
```

接下来你的 Bot 会：

1. 一次问一个，共 9 个设置问题（账号、时区、定位与内容支柱、语言、节奏、审批方式、是否用浏览器发帖、互动上限、风格样本）。回答“跳过”即使用默认值。
2. 通过 X 插件自己的 Connect 授权连接 X，绝不索要你的密码、2FA 验证码或 token。
3. 给出 Bot 名单，经你同意后创建，保存三个 skill，并建好 routines。
4. 逐个 Test run 所有 routine，最后向你汇总搭建结果和所有使用了默认值的地方。

> **前提：** 一个 Grok Bot 账号，以及一个属于你本人的 X 账号。浏览器发帖**默认关闭**。

## 会搭建什么

| 组件 | 说明 |
|---|---|
| **Bot（3–6 个）** | **素材研究员**（可按来源拆分：GitHub、论文、新闻/热帖）——搜集并核实素材。**运营官**——起草主帖和首条回复、排期、走审批，获授权后发布并记日志。**增长分析师**——只读对标研究、每日选题提示、每周复盘。 |
| **Skills** | `x-material-scout`（素材搜集与核实）、`x-draft-and-publish`（起草、审批、发布、记日志）、`x-growth-review`（相对 ER 复盘）。 |
| **Routines** | 默认工作日运行，用 `CRON_TZ` 固定时区，分钟避开整点和半点，两次运行至少隔 5 分钟，上线前先 Test run。 |
| **审批流程** | 基于文件的队列（`queue/YYYY-MM-DD/NN_slug/`），含 `main.txt`、`first_reply.txt`、`note.txt`；在一对一对话里审批，回复“发”“改：…”或“弃”；发布日志只追加不覆盖。 |
| **云电脑浏览器发帖（可选）** | 你亲自登录一次；每小时一次的 routine 通过电脑操作子任务，只发布已批准且到点的帖子；发前查重、发后截图回执，出现任何风控信号自动停 24 小时。 |

## 架构

![多 Bot 运营组：研究员、增长分析师与运营官](assets/architecture-team.jpg)

*图 1　只读的研究员和增长分析师把成果交给运营官；只有运营官能操作账号。*

![内容流水线：素材 → 起草 → 审批 → 发布 → 复盘](assets/content-pipeline.jpg)

*图 2　内容流水线。增长分析师的复盘回流到选题环节。*

设计原则：

1. **单一负责人**——每个阶段只交给一个 Bot。
2. **用文件交接**——交接时只传“路径 + 三句摘要 + 下一位负责人”。
3. **只读层与写入层分开**——只有运营官能碰账号。
4. **形成闭环**——每周复盘决定下一周的选题。

## 安全与护栏

> [!WARNING]
> X 的[开发者指南](https://docs.x.com/developer-guidelines)把官方 API 以外的自动化（包括浏览器脚本）列为可导致账号被暂停或永久封禁的行为。启用浏览器发帖，即表示你接受这一风险。

内置护栏：

- **默认人工审批。** 除非你明确划定了可自主发布的范围，任何发帖、回复、点赞、关注、私信都要先经你批准。
- **聊天里不出现凭据。** Bot 绝不索要或代填你的密码、2FA 验证码、API key 或 token；登录由你通过接管屏幕亲自完成。
- **低频、像真人。** 每天原创 1–3 条，间隔 3 小时以上；两条回复间隔 1–4 分钟；同一作者每天最多回复一条；少点赞；不批量关注；不发私信；不改主页资料。
- **自动刹车。** 出现限流、验证码、警告或临时标签，立即停止所有自动发布和互动 24 小时并暂停 routines；同一周出现两次，交由你决定。
- **主动标注。** 全自动、不经人工审核的账号，应开启 X 的“Automated”标签。
- **不做垃圾行为。** 不发重复内容，不买互动，不加入互刷回复的群（[X 开发者政策](https://docs.x.com/developer-terms/policy)）。
- **凭据边界。** 共享云电脑上的浏览器登录态，你账户下所有 Bot 都能使用；不需要时请退出登录（[审批、安全与隐私](https://docs.x.ai/grok-bot/approvals-security-and-privacy)）。

![云电脑浏览器发帖：持久登录、逐字输入、截图回执与风控刹车](assets/cloud-browser-posting.jpg)

*图 3　带护栏的可选云电脑浏览器发帖。*

## 方法论要点

这个 skill 吸收了公开、可溯源的从业者做法。它们是经验，不是平台规则，请用你自己的数据验证。完整内容见 [docs/methodology.zh-CN.md](docs/methodology.zh-CN.md)。

- **一句话主页：** 你是谁、写什么、为什么值得关注——[Justin Welsh](https://justinwelsh.me/essays/5-000-twitter-followers-90-days-1-guide)。
- **内容矩阵：** 子话题 × 5–7 种帖型，产出 75–100 个选题——[Justin Welsh](https://justinwelsh.me/essays/build-a-content-library)。
- **钩子：** 首句只有两个任务——让人停下、让人点开——[Ship 30 for 30](https://www.ship30for30.com/post/how-to-write-viral-twitter-thread-hooks-with-6-clear-examples)。
- **回复策略：** 瞄准体量是你 2–10 倍的同领域账号，在对方发帖后 15–30 分钟内回复，每条都补充新信息——[ClimbX](https://climbx.so/blog/twitter-reply-guy-strategy)。
- **为分享和回复而写：** X 开源排序代码中，复制链接分享权重 20，回复 5，点赞 0.66，举报 −234（权重乘的是预测概率）——[param.rs](https://github.com/xai-org/x-algorithm/blob/main/home-mixer/params/param.rs)。
- **远离 AI 水文：** X 因“AI 水文和回复垃圾”撤销了“infofi”类应用的 API 权限——[Nikita Bier](https://x.com/nikitabier/status/2011825522817270230)。

## 文档

| 文档 | 说明 |
|---|---|
| [`skills/x-ops-team-setup/SKILL.md`](skills/x-ops-team-setup/SKILL.md) | 双语 skill 本体 |
| [`docs/methodology.zh-CN.md`](docs/methodology.zh-CN.md) · [English](docs/methodology.md) | 方法论、算法权重、云电脑发帖教程、30 天计划 |
| [`CHANGELOG.md`](CHANGELOG.md) | 版本记录 |
| [`CONTRIBUTING.zh-CN.md`](CONTRIBUTING.zh-CN.md) · [English](CONTRIBUTING.md) | 如何参与贡献 |
| [`SECURITY.md`](SECURITY.md) | 如何私下报告安全问题 |

## 常见问题

**X 插件能替我发帖吗？**
不能。Grok Bot 的 X 插件可以读时间线、提及、书签、列表，搜索和看趋势，但目前不支持发帖。你可以自己发、使用 X 官方 API 或基于官方 API 的排程工具，或者启用可选的云电脑浏览器方案。

**会不会被封号？**
如果由你本人发布 Bot 准备好的草稿，就不涉及非 API 自动化。浏览器代发在 X 规则里属于非 API 自动化，风险客观存在；这个 skill 默认关闭它并加了护栏，但无法消除风险。

**Bot 会看到我的密码吗？**
不会。你在一对一对话里接管屏幕，亲自在云电脑浏览器里登录 X。Bot 被明确要求不索要、不输入任何凭据。

**能用在其他平台吗？**
研究、起草、复盘这几层可以直接迁移。各平台的发布规则不同，不少平台要求主动声明 AI 生成内容；在这些平台上，Bot 只做研究、草稿和复盘。详见方法论文档。

**怎么一键全停？**
在每个 Bot 信息面板的 Routines 列表里暂停；或在对话里说“Stop now”立即停止当前任务（已完成的动作不会撤销）。

**别人复刻时会拿到什么？**
只有本仓库里的 skill 文本。你的账号、登录态、电脑和对话记录都不会包含在内。

## 路线图

- [ ] 提供 `settings.md`、`style.md`、`donts.md` 示例模板
- [ ] 提供通过 X 官方 API 发帖的可选 skill 变体
- [ ] 各平台的迁移指南（仅草稿工作流）
- [ ] 周复盘报告的示例格式

欢迎通过 [功能建议](https://github.com/misselvexu/grokbot-x-ops-skill/issues/new/choose) 提出想法。

## 参与贡献

欢迎贡献！请先阅读 [CONTRIBUTING.zh-CN.md](CONTRIBUTING.zh-CN.md) 和[行为准则](CODE_OF_CONDUCT.md)。对 skill 或文档的任何修改，都必须同步更新中英文两个版本。

## 许可证

基于 [MIT 许可证](LICENSE) 发布。© 2026 misselvexu。

## 免责声明

本项目是独立的社区项目，**与 X Corp. 及 Grok Bot 的开发方均无关联，也未获其认可或赞助**。文中提及的产品名称仅用于说明。平台功能和规则会变化，遵守 [X 开发者指南](https://docs.x.com/developer-guidelines)、[X 开发者政策](https://docs.x.com/developer-terms/policy)、X 平台规则以及你所使用的任何平台的条款，是你自己的责任。本项目内容不构成法律意见。
