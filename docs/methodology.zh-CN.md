# 方法论：用 Grok Bot 运营 X 账号

[English](methodology.md) | **简体中文**

> 本文浓缩自本项目背后的研究（来源于 2026-10-22 读取）。从业者方法是经验，不是平台规则，请用你自己的数据验证。产品界面和平台规则会变化，引用任何细节前请先查看所附来源。

## 目录

1. [能力边界](#1-能力边界)
2. [值得交给 Bot 的创作者方法](#2-值得交给-bot-的创作者方法)
3. [X 排序算法与平台规则](#3-x-排序算法与平台规则)
4. [教程：云电脑浏览器发帖](#4-教程云电脑浏览器发帖)
5. [30 天落地计划](#5-30-天落地计划)
6. [迁移到其他平台](#6-迁移到其他平台)
7. [未核实事项](#7-未核实事项)

## 1. 能力边界

| 能力 | 官方说法要点 | 对运营的意义 |
|---|---|---|
| 专职 Bot | 当一项工作有独立的目标、工具、风格、审批边界或排期时，就单独建一个 Bot；从最小阵容起步（[Create and manage Bots](https://docs.x.ai/grok-bot/bots)） | 研究、起草、分析三类工作分开 |
| Bot 间协作 | Bot 之间可以发消息、建群聊，也可以通过共享文件交接（[Message and collaborate](https://docs.x.ai/grok-bot/chat-and-collaboration)） | 研究员直接把素材交给运营官，不用你转 |
| 共享云电脑 | 所有 Bot 共用一台电脑：Cookie、登录态、文件和命令行凭据都共享；每个 Bot 有自己的屏幕，但这不是安全边界（[Use the computer and apps](https://docs.x.ai/grok-bot/computer-and-apps)） | 登录一次，多个 Bot 都能用；凭据要谨慎 |
| Skills 与 Routines | skill 是可复用的做法说明；routine 让 Bot 按时间或事件自动运行，两次至少隔 5 分钟（[Skills and routines](https://docs.x.ai/grok-bot/skills-routines-and-automations)） | 把每天的工作固化并定时执行 |
| 审批 | routine 发起的审批大约 10 分钟后过期；可以用 Auto-review 规则设定“先问我”（[Approvals](https://docs.x.ai/grok-bot/approvals-security-and-privacy)） | 需要拍板的环节，排在你在线的时段 |
| X 读取与发布 | 不连接账号也能搜索读取公开内容；读私信、书签、首页时间线需要 X 插件（[Use the computer and apps](https://docs.x.ai/grok-bot/computer-and-apps)）。插件目前不支持发帖。 | 发布靠你自己、官方 API，或可选的浏览器方案 |

## 2. 值得交给 Bot 的创作者方法

### 2.1 定位与主页
- **主页三件套：** 一个好记的称号（可选）、你正在做什么、关注你能得到什么，再配清晰的头像和与简介呼应的横幅。“你必须给别人一个关注你的理由。”（[Justin Welsh](https://justinwelsh.me/essays/5-000-twitter-followers-90-days-1-guide)）
- **垂直定位：** X 在 2026 年 4 月推出 Custom Timelines，支持 75 个以上话题（[Nikita Bier](https://x.com/nikitabier/status/2046736181002645520)），并表示想鼓励小众话题（[Nikita Bier](https://x.com/nikitabier/status/2047353888282705967)）。*推断：* 话题集中的账号更容易进入对应话题的时间线。
- **衡量真实价值：** “一个 X 账号的价值，可以用它在现实生活中为你打开了哪些门来衡量。”（[Nikita Bier](https://x.com/nikitabier/status/2053182435710693493)）把带来的合作、咨询、招聘写进月度复盘。

### 2.2 内容支柱与内容矩阵
- **内容矩阵：** 列出所有子话题，再列 5–7 种风格（分步指南、预测、反常识观点、故事、观察），两者交叉；每个交叉点能写 3–4 篇，五个子话题就有 75–100 个选题（[Justin Welsh](https://justinwelsh.me/essays/build-a-content-library)）。
- **Hub-and-Spoke：** 先写一篇长内容作为轴心，再拆成 4–6 条短内容，在 4–6 周内错开发布，每条都引回轴心（[Justin Welsh](https://justinwelsh.me/essays/turn-social-media-impressions-into-dollars)）。
- **1-3-5 法：** 1 篇支柱内容 → 3 个核心观点 → 每个观点做 5 个小内容（[Justin Welsh](https://justinwelsh.me/essays/how-1-piece-of-content-becomes-16-the-1-3-5-method)）。
- **两种写作时段：** 短帖时段用来测试想法；长文时段用来推进支柱内容（[Dickie Bush](https://x.com/dickiebush/status/2112693852607799545)）。

**交给 Bot：** 把矩阵存成文件；研究员给素材标子话题；运营官按矩阵里的空格选题，避免角度重复。

### 2.3 钩子与帖型
- **首句的两个任务：** 让人停下、让人点开；做不到这两点的字都删掉（[Ship 30 for 30](https://www.ship30for30.com/post/how-to-write-viral-twitter-thread-hooks-with-6-clear-examples)）。
- **六种开头句：** 明确的断言、引人思考的问题、有争议的观点、具体的时刻、坦露脆弱的话、奇特独到的洞察（[Ship 30 for 30](https://www.ship30for30.com/post/6-proven-single-sentence-openers-to-hook-your-reader-s-attention)）。
- **写前六问：** 我在做什么承诺？解决什么问题？解决谁的问题？带来什么好处？引发什么情绪？读者下一步做什么？（[Dickie Bush](https://x.com/dickiebush/status/2109788736091287857)）
- **写得像给三年级学生看：** 用简单的词，不用术语（[Dickie Bush](https://x.com/dickiebush/status/2112877312102281255)）。
- **长串：** 最适合浓缩清单、可执行技巧和分步指南，不适合观点型论述（[Ship 30 for 30](https://www.ship30for30.com/post/the-ultimate-online-writing-republishing-framework)）；每周 1–2 条，从当月表现最好的单帖扩写（[Justin Welsh](https://justinwelsh.me/essays/5-000-twitter-followers-90-days-1-guide)）。

**长串模板（5–7 条）：**
```text
1/ 钩子：给谁看 + 讲什么 + 为什么现在值得看（一个可核对的数字或反常识结论）
2/ 背景：一句话交代问题
3/ 要点一（可附截图）
4/ 要点二
5/ 要点三 / 反例或局限
6/ 读者马上能做的清单
7/ 总结 + 一个具体的问题；来源链接放这一条或首条回复
```

### 2.4 回复策略
- **选谁回复：** 体量是你 2–10 倍、同领域、每天发帖的账号，最好在对方发帖后 15–30 分钟内回复，每天手写 10–20 条；每条都补充一个数字、反例、尖锐问题或小故事（[ClimbX](https://climbx.so/blog/twitter-reply-guy-strategy)）。
- **三圈目标：** 内圈 5–8 个同级同行，中圈 15–20 个体量更大的相邻账号，外圈 5–10 个大号偶尔回复（[VoiceMoat](https://voicemoat.com/blog/smart-reply-guy-strategy)）。
- **私密列表加通知：** 对最重要的 10 个目标打开通知（[Distribution Base](https://www.distributionbase.com/blog/channels/x-twitter/x-reply-guy-strategy)、[PostOwl](https://postowl.io/blog/x-lists-to-reply-and-grow)）。
- **平台信号：** 2026 年 7 月起，帖子在互关好友面前的可见度提高（[Nikita Bier](https://x.com/nikitabier/status/2076747704248758617)）；对互关作者帖子的回复预测有加成（当前值 15）（[BIDIRECTIONAL_BOOST_CHANGE](https://github.com/xai-org/x-algorithm/blob/main/docs/BIDIRECTIONAL_BOOST_CHANGE.md)、[Nikita Bier](https://x.com/nikitabier/status/2089763962330230803)）；回复数不影响收益分成，互刷回复群被点名（[Nikita Bier](https://x.com/nikitabier/status/2013007898226401291)）。
- **复盘指标：** 回复带来的主页访问、每 100 条回复带来的关注、开启的有效对话（[Dusan Perisic](https://rx.dusanperisic.com/blog/reply-guy-strategy-that-actually-works)）。

**交给 Bot：** 增长分析师每天推荐 3–5 条发出不到 1 小时、仍在上升的目标帖并附回复角度；由你或经你审批的运营官回复，同一作者每天最多一条。

### 2.5 节奏与时段
- Sprout Social（约 20 亿次互动）认为周二到周四 12–18 点（当地时间）最好（[Sprout Social](https://sproutsocial.com/insights/best-times-to-post-on-twitter/)）；Buffer 认为工作日 9–11 点最稳（[Buffer](https://buffer.com/resources/best-time-to-post-on-twitter-x/)）。两者冲突，两个时段各测两周。
- 起步：每天 1–2 条原创 + 1 条引用或快评，原创间隔 3 小时以上；排序会对同一作者的连续帖子打折扣（[x-algorithm](https://github.com/xai-org/x-algorithm)）。

### 2.6 公开构建、再利用与复盘
- **可分享／不分享清单：** 可以分享有效的策略、教训等商业洞察；商业机密（竞争对手能很快照搬的东西）不分享（[Arvid Kahl](https://thebootstrappedfounder.com/how-to-build-in-public-without-revealing-too-much/)）。把清单写进 `donts.md`。
- **常青帖循环：** 表现最好的旧帖每周最多重新转发一次（[Hypefury](https://hypefury.crisp.help/en/article/evergreen-posts-1ayihsk/)）。
- **指标：** 曝光、互动率、主页转化率（[Typefully](https://support.typefully.com/en/articles/8718148-analytics-page-metrics)）。坚持 30 天后，把引起共鸣的帖子扩写成长串（[Justin Welsh](https://justinwelsh.me/essays/5-000-twitter-followers-90-days-1-guide)）。
- **相对 ER：** 单帖 ER ÷ 本账号 ER 中位数；浏览不到 100 或发出不到 6 小时的不计入。

### 2.7 别人怎么用 AI，以及反面信号
| 做法 | 来源 | 要点 |
|---|---|---|
| 用 AI 生成内容矩阵 | [Justin Welsh](https://justinwelsh.me/essays/build-a-content-library) | AI 只扩展选题，写作仍由本人完成 |
| 新闻 → AI 生成 5 版 → Telegram 审批 | [n8n 模板](https://n8n.io/workflows/14842-generate-and-approve-twitter-news-tweets-with-groq-google-sheets-and-telegram/) | 多版本、按钮审批、防重复 |
| 排程与分析 | [Typefully](https://typefully.com/x-twitter)、[Hypefury](https://hypefury.crisp.help/en/article/evergreen-posts-1ayihsk/) | 走官方集成，带内容队列 |
| 周四批量起草，周五人工删改 | [实践者帖](https://x.com/HumanLoopHQ/status/2056812141253202297) | 删掉空泛内容，重写钩子 |
| 每天早上自动起草，喝咖啡时审批 | [实践者帖](https://x.com/roshanoronha/status/2074055831386263790) | “自动准备、人工拍板”的最小形态 |

**反面信号：** X 因“AI 水文和回复垃圾”撤销了奖励发帖类应用的 API 权限（[Nikita Bier](https://x.com/nikitabier/status/2011825522817270230)），并表示 For You 很大程度上依赖停留时长、点击、分享等被动信号（[Nikita Bier](https://x.com/nikitabier/status/2077173445725393345)）。

## 3. X 排序算法与平台规则

X 开源了 For You 推荐系统（[xai-org/x-algorithm](https://github.com/xai-org/x-algorithm)）。模型预测你对每条帖子做各种动作的概率，再按“权重 × 预测概率”加总。权重乘的是**预测概率**，不是实际次数，不能读成“一次举报抵多少个赞”。

**表 1　默认信号权重（[param.rs](https://github.com/xai-org/x-algorithm/blob/main/home-mixer/params/param.rs) 原值，2026-10-22 读取）**

| 正向信号 | 权重 | 负向信号 | 权重 |
|---|---|---|---|
| 通过复制链接分享 | 20 | 举报 | -234 |
| 回复 | 5 | 静音作者 | -58.8 |
| 引用 | 5 | 不感兴趣 | -52.272 |
| 私信分享 | 5 | 拉黑作者 | -31.2 |
| 关注作者 | 4 | 未停留 | -0.02 |
| 分享 | 2 | — | — |
| 转发 | 1 | — | — |
| 点赞 | 0.66 | — | — |
| 点击后停留时长 | 0.4 | — | — |
| 点击 | 0.3 | — | — |
| 打开链接 | 0.2 | — | — |
| 展开图片 / 停留 | 0.05 / 0.05 | — | — |
| 打开视频 | 0.02 | — | — |

**其他机制**（[README](https://github.com/xai-org/x-algorithm)）：超过 48 小时的帖子被过滤；同一作者第二条起打折扣；未关注作者的帖子打折扣，曝光低的新作者获得扶持；冷启动参数中帖子最大年龄为 7200 秒（[param.rs](https://github.com/xai-org/x-algorithm/blob/main/home-mixer/params/param.rs)）——*推断：* 发帖后头 2 小时最关键；代码里有专门的[回复垃圾检测流程](https://github.com/xai-org/x-algorithm/tree/main/grox/flows/reply_spam)。

**平台规则要点：**
- 禁止非 API 自动化（包括浏览器脚本），违者可被永久封禁；点赞须由用户本人直接发起；AI 自动回复需 X 事先书面批准；自动化账号须标注（[X Developer Guidelines](https://docs.x.com/developer-guidelines)）。
- 禁止为 X 上的动作给予或接受报酬（[X Developer Policy](https://docs.x.com/developer-terms/policy)）。
- 官方 API 按量付费：每条帖子 0.015 美元，带链接 0.20 美元；自助档的 API 回复只能回复“召唤”了你的帖子（[X API 定价](https://docs.x.com/x-api/getting-started/pricing)、[changelog](https://docs.x.com/changelog)）。

## 4. 教程：云电脑浏览器发帖

> [!WARNING]
> 按 [X 开发者指南](https://docs.x.com/developer-guidelines)，这属于非 API 自动化，可能导致账号被暂停或永久封禁。只有在你接受这一风险时才使用。

**原理。** Grok Bot 的云电脑带一个持久的浏览器：会话会保留，在一个 Bot 里登录后，其他 Bot 也能用（[Use the computer and apps](https://docs.x.ai/grok-bot/computer-and-apps)）。运营官不直接操作页面，而是派出一个电脑操作子任务。每个 Bot 在自己的屏幕上一次只运行一个电脑任务。

**第 1 步：登录一次。** 在你和运营官的一对一对话里打开电脑视图，接管控制，亲自登录 X 并完成 2FA，然后告诉 Bot“好了”。群聊里无法接管屏幕。Bot 不输入你的密码，也不索要验证码。会话过期或要求重新验证时，Bot 暂停并通知你，不尝试绕过。

**第 2 步：触发。** 一个每小时运行的“发帖巡检” routine（例：`CRON_TZ=<tz> 23 9-21 * * *`），只处理“已批准、已到点、没有发布标记”的帖子。routine 无法替你登录。突发热点可以走“快车道”：你批准后立即发布。

**第 3 步：子任务说明模板：**
```text
在云电脑浏览器中，X 已登录为 @<handle>。
若浏览器正被其他任务使用（编辑框半开、页面自己在变），等 2 分钟再检查。
1) 先打开 https://x.com/<handle> 查看最近的帖子：如果已有以「<正文前 12 个字>」开头的帖子，
   不要再发，只回报它的链接。
2) 打开发帖框，逐字输入以下正文（Shift+Enter 换行，段落之间空一行，不使用剪贴板）：
   <正文>
3) 若是引用帖：打开 <原帖链接> → 转发 → 引用；若有配图，从 <图片路径> 上传。
4) 核对文字、引用和图片，在 <预定时间> 之前不要点“发布”。
5) 发布后打开主页，取到新帖链接，并对帖子页截图保存到 <队列目录>。
6) 一旦出现限流、验证码、账号警告、锁定或登录提示，立即停止，不点任何按钮，回报你看到了什么。
回报：状态、帖子链接、最终文字、是否看到任何警告。
```

**第 4 步：回执与日志。** 子任务回报 `done`（完成）、`blocked`（受阻）或 `partial`（部分完成），并附链接和最终文字。运营官用 X 只读搜索回读帖子，把标记从 `PUBLISHING_BY_<bot>` 改为 `POSTED`，把文件夹移进 `published/`，追加一行日志，再把链接发给你。

**第 5 步：失败处理：**

| 情形 | 处理 |
|---|---|
| 子任务 blocked（登录、验证码） | 不原样重试；请你在一对一对话里接管屏幕 |
| 页面超时或脚本报错 | 先去主页确认是否已发出，防止发两次 |
| 两个任务同时想发同一条 | 以 `PUBLISHING_BY_<bot>` 标记为准，后到的跳过 |
| 限流、验证码、警告、临时标签 | 停止所有自动发布和互动 24 小时，暂停 routines，记风控日志，通知你；同一周两次就等你决定 |
| 会话过期 | 通知你重新登录；Bot 不输入密码 |

**六条护栏：** 节奏像真人（每天原创 1–3 条、间隔 3 小时以上，回复间隔 1–4 分钟，不整点批量发）；量要低（不批量点赞关注，不发私信，不改主页资料）；每条内容人工审核；改成全自动就开启“Automated”标签；不做垃圾行为、不互刷回复（[X Developer Policy](https://docs.x.com/developer-terms/policy)）；不需要时退出共享会话（[Approvals](https://docs.x.ai/grok-bot/approvals-security-and-privacy)）。

## 5. 30 天落地计划

| 时间 | 目标 | 关键动作 | 完成标准 |
|---|---|---|---|
| 第 1–3 天 | 定位与主页 | 一句话定位、3–5 个内容支柱、按三件套改主页 | 陌生人看主页 5 秒能说出你写什么 |
| 第 2–5 天 | 搭组 | 运行 `x-ops-team-setup`，连插件，存风格样本 | 5 条试写中你认可至少 3 条 |
| 第 4–7 天 | routines | 建排期，全部 Test run | 连续 3 天按时产出 |
| 第 6–14 天 | 跑通审批 | 草稿 → 审批 → 发布 → 回传链接 | 日志完整率 100% |
| 第 8–20 天 | 回复策略 | 建私密列表，每天 3–5 条有信息量的回复 | 记录回复带来的主页访问和关注 |
| 第 10–20 天 | 帖型测试 | 单条、清单、长串各 3 次；上午、下午各测一遍 | 周报给出相对 ER 对比 |
| 第 15–21 天 | 浏览器发帖（可选） | 你亲自登录；低频试运行；演练一次风控刹车 | 5 分钟内能暂停全部 routines |
| 第 21–28 天 | 加码与再利用 | 把前 10% 的帖子按 1-3-5 法扩写 | 新长串高于账号 ER 中位数 |
| 第 24–30 天 | 其他平台试点 | 只出草稿 | 每个平台 3 篇草稿，发布时都开启 AI 声明 |
| 第 28–30 天 | 总复盘 | 决定保留、砍掉、加码的项目 | 写出下一个 30 天计划 |

## 6. 迁移到其他平台

复用素材层和复盘层，不复用发布层；按平台重写，而不是一稿多发。不少平台要求主动声明 AI 生成内容——例如《人工智能生成合成内容标识办法》自 2025 年 9 月 1 日起施行，要求用户发布生成合成内容时主动声明（[网信办](https://www.cac.gov.cn/2025-03/14/c_1743654684782215.htm)）；小红书对使用 AI 托管工具运营的账号最重可封禁（[川观新闻](https://cbgc.scol.com.cn/news/7366379)）。在这类平台上，Bot 只做研究、草稿和复盘，发布由你本人在官方 App 里完成。

## 7. 未核实事项

- X Automation Rules 原文页面无法抓取（403），相关表述依据 X 开发者指南。
- 浏览器发帖的长期封号概率未知；小范围使用中没有遇到警告，不代表平台允许。
- 实践者给出的数字（2–10 倍、15–30 分钟、每天 10–20 条）来自博客经验，不是对照研究。
- 最佳发帖时段的研究互相冲突，样本以英文受众为主。
- “头 2 小时最关键”是根据代码参数做出的推断。
- “Automated”标签的设置路径及 Premium 对触达的影响，未能在官方页面核实。
