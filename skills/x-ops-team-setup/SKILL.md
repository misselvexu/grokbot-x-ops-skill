---
name: x-ops-team-setup
description: "Use when the owner wants Grok Bot to build an X (Twitter) account operations team from scratch: ask setup questions one at a time, connect the X plugin, create dedicated Researcher, Operator, and Growth Analyst bots, save reusable skills, and set up scheduled routines plus a draft → approve → publish flow; optionally configure cloud-browser posting with the owner's consent. Not for writing a single one-off post. ｜ 当主人想让 Grok Bot 从零搭建一个 X（Twitter）账号运营组时使用：逐一询问设置问题，连接 X 插件，创建素材研究员、运营官、增长分析师等专职 Bot，保存可复用 skill，建立定时 routines 和“草稿 → 审批 → 发布”流程；主人同意时，还可配置云电脑浏览器发帖。不适用于一次性写一条帖子。"
---

# X Ops Team Setup / X 运营组一键搭建

> **Language / 语言:** Every section gives the English instructions first, followed by the Simplified Chinese version. Both versions describe the same steps; follow whichever matches the owner's language, and reply to the owner in that language.
> 每一节先给英文说明，后给简体中文说明，两者步骤完全一致。按主人使用的语言执行，并用该语言回复主人。

**EN —** You are the owner's main bot. Build an X operations team in the order below. After each step, tell the owner in one or two sentences what you did and what comes next. Never invent numbers, features, or UI paths. If you are unsure about a step, say so plainly and ask the owner to confirm in the interface.

**中文 —** 你是主人的主 Bot。按下面的顺序把一套 X 运营组搭起来。每一步完成后用一两句话告诉主人做了什么、下一步是什么。全程不编造数字、功能和界面路径；没有把握的步骤，如实说明并请主人在界面里确认。

---

## 0. Read the rules first / 先读规则

**EN**
- Before creating any scheduled task, read the `routines` skill. Before using the browser or desktop, read the `box-desktop` skill. When you hit a login, a captcha, or a password, read the `sign-in` skill first. Read them before you act.
- Never ask the owner for their X password, 2FA code, API key, or token, and never type any of these into a browser on their behalf. The X plugin is connected only through its own Connect authorization.
- Outward-facing actions (posting, replying, liking, following, DMs) require the owner's approval by default, unless the owner explicitly chose "may publish autonomously" in Step 1 and defined the scope.

**中文**
- 需要建定时任务前，先读 `routines` 技能；需要用浏览器或桌面前，先读 `box-desktop` 技能；遇到登录、验证码或密码，先读 `sign-in` 技能。读完再动手。
- 绝不向主人索要 X 的密码、2FA 验证码、API key 或 token，也不替主人在浏览器里输入这些信息。X 插件只走它自己的 Connect 授权。
- 对外动作（发帖、回复、点赞、关注、私信）默认需要主人审批，除非主人在第 1 步明确选择了“可自主发”，并给出了范围。

## 1. Setup questions (one at a time) / 逐个问设置问题（一次只问一个）

**EN** — Ask in order and wait for each answer before asking the next. If the owner says "skip", use the default in parentheses and flag it in the final summary.
1. Which X account will be operated? (@handle)
2. What is the owner's time zone? All routines are scheduled in it. (Default: the time zone in the owner's Grok Bot settings)
3. Positioning: in one sentence, "who you are, what you write about, and what readers get by following you", plus 3–5 content pillars (sub-topics).
4. Posting language: Chinese, English, or bilingual?
5. Cadence: how many original posts and how many quotes or quick takes per day? Minimum gap between two original posts? (Default: 1–2 originals per day, ≥3 hours apart)
6. Approval mode: A. review every post first (default); B. certain types may be published autonomously — the owner must list which types; C. drafts only, the owner publishes.
7. Use the cloud-browser to publish on the owner's behalf? (Default: no. If "yes", run Step 7, and read the Step 7 risk notice to the owner first.)
8. Engagement caps: maximum replies and likes per day? Stay away from follows and DMs entirely? (Default: ≤10 replies, ≤20 likes, no automated follows, no DMs)
9. Any style samples, off-limits topics, or items that must be verified? (Ask the owner to paste 3–5 past posts they are happy with.)

Once all questions are answered, compile the answers into an "Operations Settings" summary and ask the owner to confirm. After confirmation, save it to `<workdir>/config/settings.md` in the shared workspace (`<workdir>` defaults to `x-ops/`), save the style samples as `<workdir>/config/style.md`, and save the off-limits list as `<workdir>/config/donts.md`.

**中文** — 按顺序提问，等主人回答后再问下一个。主人说“跳过”就用括号里的默认值，并在最后的汇总里标出来。
1. 要运营的 X 账号是哪个？（@handle）
2. 主人在哪个时区？routines 都按这个时区排。（默认：主人在 Grok Bot 设置里的时区）
3. 账号定位：一句话说清“你是谁、写什么、读者关注你能得到什么”，再列 3–5 个内容支柱（子话题）。
4. 发帖语言：中文、英文还是双语？
5. 发帖节奏：每天几条原创、几条引用或快评？两条原创至少隔多久？（默认：每天 1–2 条原创，间隔 ≥3 小时）
6. 审批方式：A. 每条都先过目（默认）；B. 某些类型可以自主发，请主人写清是哪些类型；C. 只要草稿，主人自己发。
7. 是否用云电脑浏览器代为发帖？（默认：否。选“是”就执行第 7 步，并先把第 7 步的风险说明念给主人听）
8. 互动上限：每天最多回复几条、点赞几次？关注和私信是否完全不碰？（默认：回复 ≤10 条，点赞 ≤20 次，不自动关注，不发私信）
9. 有没有风格样本、禁写话题、必须核实的事项？（让主人贴 3–5 条自己满意的旧帖）

问完后，把所有答案整理成一份“运营设定”，请主人确认。确认后存进共享工作区的 `<workdir>/config/settings.md`（`<workdir>` 默认是 `x-ops/`），同时把风格样本存成 `<workdir>/config/style.md`，禁忌清单存成 `<workdir>/config/donts.md`。

## 2. Connect the X plugin / 连接 X 插件

**EN**
- First check whether the X plugin is already installed. If not, find and install it via plugin search (use the `SearchPlugins` / `InstallPlugin` tools if available; otherwise ask the owner to open **Connect apps** in the sidebar, find the X plugin, and choose **Add**).
- For authorization, ask the owner to click Connect on the X card and authorize with their own X account. You never touch the password.
- Tell the owner what the plugin can do: read the home timeline, mentions, bookmarks, and lists; search public posts; view trends. Also be clear about what it cannot do: the plugin does not currently support posting. Publishing therefore has only two paths: the owner posts manually, or the browser option in Step 7.
- Public reads are rate-limited and the quota is shared across the whole account (rely on the quota hints the tools return). Record in the settings file roughly how many calls each bot may use per day.

**中文**
- 先确认 X 插件是否已经装好。没装就用插件搜索找到 X 插件并安装（有 `SearchPlugins` / `InstallPlugin` 工具时用它们；没有就请主人打开侧边栏的 **Connect apps**，找到 X 插件后选择 **Add**）。
- 授权时，请主人在 X 卡片上点 Connect，用自己的 X 账号授权。你不碰密码。
- 告诉主人插件能做什么：读主页时间线、提及、书签、列表，搜索公开帖子，看趋势。也要说清插件不能做什么：插件目前不支持发帖。所以发布只有两条路：主人自己发，或者走第 7 步的浏览器方案。
- 公开读取有额度，全账户共享（以工具返回的额度提示为准）。在设定文件里写清每个 Bot 每天大约能用多少次。

## 3. Create dedicated bots / 创建专职 Bot

**EN** — Show the owner this roster with a one-line role for each bot, and create them only after the owner agrees. Keep the roster small: at least 3, at most 6 bots.

| Bot | Responsibility (goes into the bot description) | Never does |
|---|---|---|
| Researcher (may be split by source into 1–3 bots, e.g. GitHub Researcher, Paper Researcher, News/Trending Watcher) | Every day, following the owner's content pillars, picks the 3 most post-worthy items from the assigned sources, opens the originals to verify numbers and dates, and writes a sourced material report | Posting, engaging, inventing numbers |
| Operator | Reads the day's material reports and growth hints, drafts the main post and first reply per the style file, schedules them, and runs approval; publishes and logs when the owner allows | Publishing without approval; tagging accounts whose identity is unverified |
| Growth Analyst | Read-only on public data: studies peer accounts in the niche, reviews the account's own posts, delivers 2–3 topic hints and 3–5 posts worth replying to each day, plus a weekly review | Posting, liking, following, DMs |

- If you can create bots, create them directly with a name and description. If not, hand the names and descriptions to the owner and ask them to choose **New** in the sidebar, then **Create new Bot**, and paste the description via **Edit Profile** in the bot menu.
- Every bot description must state four things: the outcome it owns, its data sources, where it delivers (file path plus recipient), and what it never does.
- If handoffs should be visible to everyone, create a group chat with these bots (2–6 bots). Do not run approvals in the group chat; keep them in the one-on-one chat between the owner and the Operator.

**中文** — 先给主人看这份名单和每个 Bot 的一句话职责，主人同意后再建。名单宁小勿大，最少 3 个，最多 6 个：

| Bot | 职责（写进 Bot 描述） | 永远不做 |
|---|---|---|
| 素材研究员（可按来源拆成 1–3 个：如 GitHub 研究员、论文研究员、新闻/热帖观察员） | 每天按主人的内容支柱，从指定来源挑 3 条最值得写的素材，打开原文核实数字和日期，写成带链接的素材报告 | 不发帖，不互动，不编数字 |
| 运营官 | 读当天的素材报告和增长提示，按风格文件起草主帖和首条回复，排期，走审批；主人同意时负责发布和记日志 | 未经审批不发；不 tag 身份未核实的账号 |
| 增长分析师 | 只读公开数据：研究同领域对标账号，复盘自家帖子，每天给 2–3 个选题提示和 3–5 条值得回复的帖子，每周出复盘 | 不发帖、不点赞、不关注、不私信 |

- 你有创建 Bot 的能力时，直接创建并写好名称和描述；没有时，把名称和描述交给主人，请主人在侧边栏选 **New**，再选 **Create new Bot** 创建，然后在 Bot 菜单里用 **Edit Profile** 粘贴描述。
- 每个 Bot 的描述都写清四件事：负责的结果、数据源、交付到哪里（文件路径加交给谁）、永远不做什么。
- 需要大家看到交接时，再建一个群聊，把这几个 Bot 拉进去（2–6 个 Bot）。审批不要放在群聊里，放在主人和运营官的一对一对话里。

## 4. Save reusable skills / 保存可复用的 skill

**EN** — Have each bot complete its task manually once; after the owner signs off, save it as a skill. Skills contain only generic steps with `<parameter>` placeholders; "which bot, what time, which directory" belongs in the routine, not the skill. Every skill must state: when to use it, required inputs, step order, how to verify, what it returns, and which step needs approval. Save these three:
- `x-material-scout`: gathering and verifying material. Output: `<workdir>/reports/<source>/YYYY-MM-DD.md`. If today's report already exists, stop; do not deliver twice.
- `x-draft-and-publish`: topic selection, drafting, approval, publishing, and logging. See Steps 6 and 7.
- `x-growth-review`: read-only review of peer accounts and the account's own posts. Compute engagement rate ER = (likes + reposts + replies + quotes) ÷ views, and compare using relative ER (post ER ÷ the account's median ER). Exclude posts with fewer than 100 views; exclude posts younger than 6 hours from comparisons; write "not available" for any metric you cannot obtain.

**中文** — 先让每个 Bot 手动跑通一次自己的任务，主人认可后，再存成 skill。skill 里只写通用步骤，用 `<参数>` 占位；“哪个 Bot、几点运行、存到哪个目录”写进 routine，不写进 skill。每个 skill 都要写清：什么时候用、需要什么输入、步骤顺序、怎么核验、返回什么、哪一步需要审批。建议存三个：
- `x-material-scout`：素材搜集与核实。输出 `<workdir>/reports/<来源>/YYYY-MM-DD.md`。当天的报告已经存在就停下，不重复交付。
- `x-draft-and-publish`：选题、起草、审批、发布、记日志。见第 6、7 步。
- `x-growth-review`：对标账号与自家帖子的只读复盘。计算互动率 ER =（点赞 + 转发 + 回复 + 引用）÷ 浏览，用相对 ER（单帖 ER ÷ 该账号 ER 中位数）比较。浏览少于 100 的不算；发出不到 6 小时的不进对比；拿不到的指标写“拿不到”。

## 5. Create routines (each bot in its own chat) / 建 routines（每个 Bot 在自己的对话里建）

**EN**
- Read the `routines` skill before creating any, and follow its conventions: cron uses 5 fields; prefix `CRON_TZ=<owner's time zone>` to pin the time zone; avoid minutes 0 and 30 — use the minute at which the owner made the request, or a nearby odd minute; keep at least 5 minutes between runs; run on weekdays during daytime by default, and justify any weekend or night runs.
- A routine prompt describes the outcome to achieve, not hard-coded tool parameters. Its last line states who receives the result, in which app, and what to do when there is nothing new.
- Reference schedule (replace times with the owner's routine; examples only):

| Bot | When | What |
|---|---|---|
| Researcher | Weekday mornings (e.g. `CRON_TZ=<tz> 7 7 * * 1-5`) | Produce today's material report; send the path and a three-sentence summary to the Operator |
| Growth Analyst | About 40 minutes after the Researcher (e.g. `CRON_TZ=<tz> 47 7 * * 1-5`) | Today's topic hints and posts worth replying to |
| Operator | When the owner is usually online (e.g. `CRON_TZ=<tz> 17 8 * * 1-5`) | Merge inputs, draft, send for approval |
| Operator (only if Step 7 is enabled) | Hourly within the posting window (e.g. `CRON_TZ=<tz> 23 9-21 * * *`; reason: the owner sets the posting window, which may include weekends) | Check the queue and publish approved posts whose time has come |
| Growth Analyst | Monday mornings (e.g. `CRON_TZ=<tz> 7 10 * * 1`) | Weekly review and 3 actionable adjustments |

- Test run every routine once to confirm it picks up today's inputs, stops at the expected approval point, and explains failures clearly. Only then save it as a recurring routine.
- Remind the owner of two things: approval cards raised by a routine expire after about 10 minutes, so schedule decision points when the owner is online; and routines may be paused if they go unanswered for a long time.

**中文**
- 建之前先读 `routines` 技能，按它的规矩写：cron 是 5 段式；在前面加 `CRON_TZ=<主人时区>` 固定时区；分钟避开 0 和 30，取主人提出需求那一刻的分钟数或相邻的奇数分钟；两次运行至少隔 5 分钟；默认只在工作日、白天运行，周末或夜间运行要说明理由。
- routine 的提示词写“要做成什么”，不写死工具参数。最后一行写清结果交给谁、在哪个 App 里，以及没有新内容时怎么办。
- 参考排期（把时间换成主人的作息，示例）：

| Bot | 时间 | 做什么 |
|---|---|---|
| 素材研究员 | 工作日早上（例：`CRON_TZ=<tz> 7 7 * * 1-5`） | 产出当天的素材报告，把路径和三句摘要交给运营官 |
| 增长分析师 | 研究员之后约 40 分钟（例：`CRON_TZ=<tz> 47 7 * * 1-5`） | 当日选题提示和值得回复的帖子 |
| 运营官 | 主人通常在线的时段（例：`CRON_TZ=<tz> 17 8 * * 1-5`） | 合并起草，发审批 |
| 运营官（仅在第 7 步启用时） | 发帖时段内每小时一次（例：`CRON_TZ=<tz> 23 9-21 * * *`，理由：发帖时段由主人指定，可能包括周末） | 检查队列，把到点且已批准的帖子发出去 |
| 增长分析师 | 每周一上午（例：`CRON_TZ=<tz> 7 10 * * 1`） | 周复盘和 3 条可执行调整 |

- 每个 routine 都先 Test run 一次，确认它取的是当天的输入、停在了预期的审批点、失败时说得清原因。之后再保存为长期运行。
- 提醒主人两件事：一是由 routine 发起的审批卡大约 10 分钟后会过期，所以要主人拍板的环节，排在主人在线的时段；二是长时间没人回应时，routines 可能被暂停。

## 6. Draft → Approve → Publish / 草稿 → 审批 → 发布

**EN**
1. The Operator places each draft in `<workdir>/queue/YYYY-MM-DD/NN_slug/`: `main.txt` holds the post body, `first_reply.txt` the first reply (links and sources), and `note.txt` the sources, suggested publish time, and points to verify; images go alongside. The day's schedule goes in `PLAN.md`.
2. Send the approval message in the one-on-one chat with the owner: body, source links, suggested time, and risks. The owner replies "post", "edit: …", or "drop".
3. In approval mode C, the owner publishes and pastes the link back. In modes A or B, publish per Step 7.
4. Before publishing, place a `PUBLISHING_BY_<bot>` marker in the post folder; if you see another bot's marker, skip the post. After publishing, change it to a `POSTED` marker, move the folder into `published/`, and append a line to `<workdir>/logs/originals_log.tsv`: time with time zone, type, link, notes.
5. Write posts per the Step 1 settings: open with a judgment, follow with verifiable facts, give readers something they can do right away, and end with a specific question. Re-check every number, date, and quote against the original source.

**中文**
1. 运营官把每条草稿放进 `<workdir>/queue/YYYY-MM-DD/NN_slug/`：`main.txt` 是正文，`first_reply.txt` 是首条回复（放链接和来源），`note.txt` 记来源、建议发布时间和需要核实的点，配图另放。当天的排期写进 `PLAN.md`。
2. 在和主人的一对一对话里发审批消息：正文、来源链接、建议时间和风险点。主人回复“发”“改：…”或“弃”。
3. 审批方式是 C 时，主人自己发完把链接贴回来；是 A 或 B 时，按第 7 步发布。
4. 发布前在帖子文件夹里放 `PUBLISHING_BY_<bot>` 标记，看到别人的标记就跳过。发完改成 `POSTED` 标记，把文件夹移进 `published/`，并往 `<workdir>/logs/originals_log.tsv` 追加一行：时间带时区、类型、链接、说明。
5. 写帖子按第 1 步的设定：第一句给判断，然后是可核对的事实，再给读者马上能做的事，结尾提一个具体的问题。数字、日期和引述，逐条对原文再核一遍。

## 7. (Optional) Cloud-browser posting / （可选）云电脑浏览器发帖

**EN** — Run this step only if the owner answered "yes" in Step 1. Read the full risk notice below to the owner first, and continue only after they confirm.
- **Risk notice:** X's developer rules list automation outside the official API (including browser scripts) as behavior that can lead to account suspension or permanent bans. The X plugin itself also states that the bot must not log in to X in the browser on the owner's behalf. The login in this step must therefore be done by the owner personally, volume must stay low, the cadence must look human, and content must be reviewed by a person. Fully automated accounts without human review should enable the "Automated" label on X.
- **Log in once, stay logged in:** In the one-on-one chat with you, ask the owner to open the computer view, take control of the screen, log in to X in the cloud computer's browser personally, complete 2FA, and then tell you "done". Screen takeover is not available in group chats, so this must happen in a one-on-one chat. The browser session persists and other bots under the same account can use it.
- **How to publish:** Dispatch a computer-use subtask to publish. Its instructions must state:
  - The browser is already logged in as @handle;
  - If the browser is in use by another task, wait 2 minutes and check again;
  - First open @handle's profile to check for duplicates; if a post with the same opening already exists, do not post — report its link only;
  - Type the body character by character, use Shift+Enter for line breaks, and do not use the clipboard;
  - Verify the text, any quoted post, and images; do not click "Post" before the scheduled time;
  - After posting, get the new post's link from the profile and save a screenshot of the post page to the post folder;
  - On any rate limit, captcha, account warning, lock, or login prompt, stop immediately, click nothing, and report what you saw.
- **Trigger:** The hourly Operator routine from Step 5 checks the queue and publishes only posts that are "approved, due, and unmarked". A routine cannot log in or enter passwords for the owner; when the session expires, ask the owner in chat to take control of the screen and log in again.
- **Receipt and verification:** After the subtask reports back, read the post back with X's read-only search, verify the opening and link, log it, and send the link to the owner.
- **Failure handling:**
  - If the subtask reports `blocked`, do not retry as-is. If it is a login or captcha issue, ask the owner to take control of the screen; otherwise, tell the owner the reason.
  - On a page timeout or error, first check the profile to see whether the post went out, then decide whether to post again.
  - On a rate limit, captcha, warning, or temporary label: stop all automated posting and engagement for 24 hours, pause the related routines, record it in `<workdir>/logs/risk_events.tsv`, and notify the owner. If it happens twice in the same week, wait for the owner's decision.
- **Engagement boundaries:** Replies must read like a person wrote them: specific information, no template phrases, 1–4 minutes between replies, at most one reply per author per day, and reply content follows the approval mode. Like sparingly; no bulk follows, no DMs, no profile edits.

**中文** — 只在主人第 1 步选择“是”时执行。先把下面的风险说明完整告诉主人，主人确认后才继续。
- **风险说明：** X 的开发者规则把官方 API 之外的自动化（包括浏览器脚本）列为可导致账号被暂停或永久封禁的行为。X 插件本身也规定：Bot 不替主人在浏览器里登录 X。所以这一步的登录必须由主人亲手完成，发布量要低，节奏要像真人，内容必须经过人工审核。全自动、不经人工审核的账号，应在 X 上开启“Automated”标签。
- **登录一次，持久保持：** 请主人在和你的一对一对话里打开电脑视图，接管屏幕，在云电脑的浏览器里亲自登录 X，完成 2FA 后告诉你“好了”。群聊里没法接管屏幕，必须在一对一对话里做。浏览器会话会保留，你账户下的其他 Bot 也能用。
- **发布方式：** 派一个电脑操作子任务完成发布。任务说明里写清：
  - 浏览器里已经登录了 @handle；
  - 如果浏览器正被其他任务占用，等 2 分钟再看；
  - 先打开 @handle 的主页查重，已经有同样开头的帖子就不发，只回报链接；
  - 逐字输入正文，用 Shift+Enter 换行，不用剪贴板；
  - 核对文字、引用的原帖和配图，不早于预定时间点“发布”；
  - 发完到主页取新帖的链接，并对帖子页截一张图存进帖子文件夹；
  - 一旦看到限流、验证码、账号警告、锁定或登录提示，立即停下，什么都不点，回报看到了什么。
- **触发：** 由第 5 步那个每小时一次的运营官 routine 检查队列，只发“已批准、到点、没有发布标记”的帖子。routine 无法替主人登录，也无法填写密码；会话过期时，就在对话里请主人接管屏幕重新登录。
- **回执与核对：** 子任务回报后，用 X 的只读搜索回读这条帖子，核对开头和链接，记日志，然后把链接发给主人。
- **失败处理：**
  - 子任务回报 blocked 时不要原样重试。是登录或验证码问题，就请主人接管屏幕；是其他原因，就把原因告诉主人。
  - 页面超时或报错时，先去主页确认帖子是否已经发出，再决定要不要重发。
  - 遇到限流、验证码、警告或临时标签：停掉所有自动发布和互动 24 小时，暂停相关 routines，记进 `<workdir>/logs/risk_events.tsv`，并告诉主人；同一周出现两次，就等主人决定。
- **互动边界：** 回复要像真人：有具体信息，不用模板句，两条之间隔 1–4 分钟，一个作者一天最多回一条，回复内容按审批方式处理。点赞要少，不批量关注，不发私信，不改主页资料。

## 8. Wrap-up / 收尾

**EN**
- Summarize for the owner: which bots were created, which skills were saved, which routines were set up (times with time zone), the approval mode, whether browser posting is enabled, and every place a default was used.
- Explain how to pause all automation: pause the routines from the Routines list in each bot's info panel.
- During the first week, send the owner the drafts awaiting approval every day. On day 7, ask the Growth Analyst for the first review, and decide together with the owner what to keep, what to cut, and where to double down.

**中文**
- 向主人汇总：建了哪些 Bot、存了哪些 skill、建了哪些 routines（时间带时区）、审批方式、是否启用浏览器发布，以及所有用了默认值的地方。
- 写明暂停全部自动化的办法：在每个 Bot 的信息面板的 Routines 列表里暂停。
- 第一周每天把待批准的草稿发给主人；第七天请增长分析师出第一份复盘，和主人一起决定保留什么、砍掉什么、在哪里加码。
