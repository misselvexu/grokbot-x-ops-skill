# Methodology: Running an X Account with Grok Bot

**English** | [简体中文](methodology.zh-CN.md)

> Condensed from the research behind this project (sources read on 2026-10-22). Practitioner methods are experience, not platform rules — validate them with your own data. Product UIs and rules change; check the linked sources before relying on any detail.

## Contents

1. [Capability boundaries](#1-capability-boundaries)
2. [Creator methods worth automating](#2-creator-methods-worth-automating)
3. [The X ranking algorithm and platform rules](#3-the-x-ranking-algorithm-and-platform-rules)
4. [Tutorial: cloud-browser posting](#4-tutorial-cloud-browser-posting)
5. [30-day rollout plan](#5-30-day-rollout-plan)
6. [Adapting to other platforms](#6-adapting-to-other-platforms)
7. [Known gaps](#7-known-gaps)

## 1. Capability boundaries

| Capability | What the docs say | Why it matters |
|---|---|---|
| Dedicated bots | Create a separate bot when a job has its own goal, tools, style, approval boundary, or schedule; start with the smallest roster ([Create and manage Bots](https://docs.x.ai/grok-bot/bots)) | Keep research, drafting, and analysis apart |
| Bot collaboration | Bots can message each other, join group chats, and hand off through shared files ([Message and collaborate](https://docs.x.ai/grok-bot/chat-and-collaboration)) | Researchers hand material to the Operator without you relaying it |
| Shared cloud computer | All bots share one computer — cookies, logins, files, and CLI credentials; each bot has its own screen, but that is not a security boundary ([Use the computer and apps](https://docs.x.ai/grok-bot/computer-and-apps)) | Log in once for every bot; treat credentials with care |
| Skills & routines | A skill is a reusable procedure; a routine runs a bot on a schedule or event, at least 5 minutes apart ([Skills and routines](https://docs.x.ai/grok-bot/skills-routines-and-automations)) | Turn daily work into scheduled work |
| Approvals | Approvals raised by routines expire after about 10 minutes; Auto-review rules can be set to "ask me first" ([Approvals](https://docs.x.ai/grok-bot/approvals-security-and-privacy)) | Schedule decision points when you are online |
| X reads vs. posting | Public X content can be searched without connecting an account; DMs, bookmarks, and the home timeline need the X plugin ([Use the computer and apps](https://docs.x.ai/grok-bot/computer-and-apps)). The plugin does not currently support posting. | Publish yourself, via the official API, or via the optional browser flow |

## 2. Creator methods worth automating

### 2.1 Positioning and profile
- **Profile in three parts:** an optional memorable title, what you are working on, and what followers get — plus a clear avatar and a banner that echoes the bio. "You have to give people a reason to follow you." ([Justin Welsh](https://justinwelsh.me/essays/5-000-twitter-followers-90-days-1-guide))
- **Niche focus:** X launched Custom Timelines with 75+ topics in April 2026 ([Nikita Bier](https://x.com/nikitabier/status/2046736181002645520)) and said it wants to encourage niche topics ([Nikita Bier](https://x.com/nikitabier/status/2047353888282705967)). *Inference:* focused accounts are more likely to surface in topic timelines.
- **Measure real value:** "the value of an X account can be measured by the doors it opens for you in real life" ([Nikita Bier](https://x.com/nikitabier/status/2053182435710693493)). Track collaborations, inquiries, and hiring leads in your monthly review.

### 2.2 Content pillars and the content matrix
- **Content matrix:** list every sub-topic, list 5–7 styles (step-by-step guide, prediction, contrarian take, story, observation), and cross them; each cell yields 3–4 posts, so five sub-topics give 75–100 ideas ([Justin Welsh](https://justinwelsh.me/essays/build-a-content-library)).
- **Hub-and-spoke:** write one long piece (the hub), then 4–6 short spokes released over 4–6 weeks, each linking back ([Justin Welsh](https://justinwelsh.me/essays/turn-social-media-impressions-into-dollars)).
- **1-3-5 method:** 1 pillar piece → 3 core ideas → 5 small pieces per idea ([Justin Welsh](https://justinwelsh.me/essays/how-1-piece-of-content-becomes-16-the-1-3-5-method)).
- **Two writing modes:** short-form sessions to test ideas; long-form sessions to build a pillar piece ([Dickie Bush](https://x.com/dickiebush/status/2112693852607799545)).

**Bot handoff:** store the matrix as a file; Researchers tag material by sub-topic; the Operator fills empty cells so angles do not repeat.

### 2.3 Hooks and formats
- **Two jobs of the first line:** stop the scroll and earn the click; cut every word that does neither ([Ship 30 for 30](https://www.ship30for30.com/post/how-to-write-viral-twitter-thread-hooks-with-6-clear-examples)).
- **Six single-sentence openers:** a bold claim, a thought-provoking question, a controversial take, a specific moment, a vulnerable admission, an unusual insight ([Ship 30 for 30](https://www.ship30for30.com/post/6-proven-single-sentence-openers-to-hook-your-reader-s-attention)).
- **Six warm-up questions:** what promise am I making, what problem, for whom, what benefit, what emotion, what should the reader do next ([Dickie Bush](https://x.com/dickiebush/status/2109788736091287857)).
- **Write at a third-grade level:** simple words, no jargon ([Dickie Bush](https://x.com/dickiebush/status/2112877312102281255)).
- **Threads:** best for dense lists, actionable tips, and step-by-step guides, not opinion essays ([Ship 30 for 30](https://www.ship30for30.com/post/the-ultimate-online-writing-republishing-framework)); 1–2 per week, expanded from the month's best single posts ([Justin Welsh](https://justinwelsh.me/essays/5-000-twitter-followers-90-days-1-guide)).

**Thread template (5–7 posts):**
```text
1/ Hook: for whom + what + why now (a checkable number or counterintuitive finding)
2/ Context: the problem in one sentence
3/ Point one (screenshot optional)
4/ Point two
5/ Point three / counterexample or limitation
6/ A checklist readers can use right away
7/ Summary + one specific question; sources here or in the first reply
```

### 2.4 Reply strategy
- **Who to reply to:** same-niche accounts 2–10× your size that post daily, ideally within 15–30 minutes of their post, 10–20 handwritten replies a day; every reply adds a number, counterexample, sharp question, or short story ([ClimbX](https://climbx.so/blog/twitter-reply-guy-strategy)).
- **Three circles:** 5–8 peers, 15–20 larger adjacent accounts, 5–10 large accounts replied to occasionally ([VoiceMoat](https://voicemoat.com/blog/smart-reply-guy-strategy)).
- **Private lists + notifications** for the top 10 targets ([Distribution Base](https://www.distributionbase.com/blog/channels/x-twitter/x-reply-guy-strategy), [PostOwl](https://postowl.io/blog/x-lists-to-reply-and-grow)).
- **Platform signals:** since July 2026, posts are more visible to mutuals ([Nikita Bier](https://x.com/nikitabier/status/2076747704248758617)); reply predictions on posts from mutuals get a boost (current value 15) ([BIDIRECTIONAL_BOOST_CHANGE](https://github.com/xai-org/x-algorithm/blob/main/docs/BIDIRECTIONAL_BOOST_CHANGE.md), [Nikita Bier](https://x.com/nikitabier/status/2089763962330230803)); reply counts do not affect revenue share, and reply-trading groups were called out ([Nikita Bier](https://x.com/nikitabier/status/2013007898226401291)).
- **Metrics:** profile visits from replies, follows per 100 replies, real conversations started ([Dusan Perisic](https://rx.dusanperisic.com/blog/reply-guy-strategy-that-actually-works)).

**Bot handoff:** the Growth Analyst suggests 3–5 rising target posts under an hour old, with angles; you (or the approved Operator) reply, at most once per author per day.

### 2.5 Cadence and timing
- Sprout Social (≈2B engagements) favors Tue–Thu, 12:00–18:00 local ([Sprout Social](https://sproutsocial.com/insights/best-times-to-post-on-twitter/)); Buffer favors weekdays 9:00–11:00 ([Buffer](https://buffer.com/resources/best-time-to-post-on-twitter-x/)). The findings conflict — test both windows for two weeks.
- Start with 1–2 originals plus 1 quote or quick take per day, ≥3 hours apart; the ranker discounts consecutive posts from the same author ([x-algorithm](https://github.com/xai-org/x-algorithm)).

### 2.6 Build in public, repurposing, and review
- **Share / don't share list:** share business insights such as strategies that work and lessons learned; keep trade secrets — anything a competitor could quickly copy — private ([Arvid Kahl](https://thebootstrappedfounder.com/how-to-build-in-public-without-revealing-too-much/)). Put this list in `donts.md`.
- **Evergreen recycling:** re-share top posts at most once a week ([Hypefury](https://hypefury.crisp.help/en/article/evergreen-posts-1ayihsk/)).
- **Metrics:** impressions, engagement rate, profile conversion ([Typefully](https://support.typefully.com/en/articles/8718148-analytics-page-metrics)). After 30 days, expand the posts that resonated into threads ([Justin Welsh](https://justinwelsh.me/essays/5-000-twitter-followers-90-days-1-guide)).
- **Relative ER:** post ER ÷ the account's median ER; skip posts under 100 views or younger than 6 hours.

### 2.7 How others use AI — and the warning sign
| Practice | Source | Takeaway |
|---|---|---|
| AI-generated content matrix | [Justin Welsh](https://justinwelsh.me/essays/build-a-content-library) | AI expands ideas; you still write |
| News → 5 AI variants → Telegram approval | [n8n template](https://n8n.io/workflows/14842-generate-and-approve-twitter-news-tweets-with-groq-google-sheets-and-telegram/) | Multiple variants, button approval, de-duplication |
| Scheduling and analytics | [Typefully](https://typefully.com/x-twitter), [Hypefury](https://hypefury.crisp.help/en/article/evergreen-posts-1ayihsk/) | Official integrations with queues |
| Batch-draft Thursday, human edit Friday | [Practitioner post](https://x.com/HumanLoopHQ/status/2056812141253202297) | Cut anything generic; rewrite hooks |
| Auto-draft every morning, approve over coffee | [Practitioner post](https://x.com/roshanoronha/status/2074055831386263790) | The minimal "prepare automatically, decide manually" loop |

**Warning sign:** X revoked API access for post-rewarding apps over "AI slop and reply spam" ([Nikita Bier](https://x.com/nikitabier/status/2011825522817270230)), and said For You relies heavily on passive signals like dwell time, clicks, and shares ([Nikita Bier](https://x.com/nikitabier/status/2077173445725393345)).

## 3. The X ranking algorithm and platform rules

X open-sourced its For You recommender ([xai-org/x-algorithm](https://github.com/xai-org/x-algorithm)). It predicts the probability of each action and sums *weight × predicted probability*. Weights multiply **predicted probabilities**, not counts — do not read them as "one report equals N likes".

**Table 1. Default signal weights ([param.rs](https://github.com/xai-org/x-algorithm/blob/main/home-mixer/params/param.rs), read 2026-10-22)**

| Positive signal | Weight | Negative signal | Weight |
|---|---|---|---|
| Share via copy link | 20 | Report | -234 |
| Reply | 5 | Mute author | -58.8 |
| Quote | 5 | Not interested | -52.272 |
| Share via DM | 5 | Block author | -31.2 |
| Follow author | 4 | No dwell | -0.02 |
| Share | 2 | — | — |
| Repost | 1 | — | — |
| Like | 0.66 | — | — |
| Dwell time after click | 0.4 | — | — |
| Click | 0.3 | — | — |
| Open link | 0.2 | — | — |
| Photo expand / dwell | 0.05 / 0.05 | — | — |
| Video open | 0.02 | — | — |

**Other mechanics** ([README](https://github.com/xai-org/x-algorithm)): posts older than 48 hours are filtered; the second post onward from the same author is discounted; out-of-network posts are discounted while low-exposure new authors get a boost; a cold-start parameter sets a max post age of 7200 seconds ([param.rs](https://github.com/xai-org/x-algorithm/blob/main/home-mixer/params/param.rs)) — *inference:* the first two hours matter most; there is a dedicated [reply-spam flow](https://github.com/xai-org/x-algorithm/tree/main/grox/flows/reply_spam).

**Platform rules:**
- Non-API automation, including browser scripts, can lead to permanent suspension; likes must be initiated by the user; AI auto-replies need prior written approval from X; automated accounts must be labeled ([X Developer Guidelines](https://docs.x.com/developer-guidelines)).
- No paying or being paid for actions on X ([X Developer Policy](https://docs.x.com/developer-terms/policy)).
- The official API is pay-per-use: $0.015 per post, $0.20 with a link; self-serve API replies may only answer posts that summoned you ([X API pricing](https://docs.x.com/x-api/getting-started/pricing), [changelog](https://docs.x.com/changelog)).

## 4. Tutorial: cloud-browser posting

> [!WARNING]
> This is non-API automation under the [X Developer Guidelines](https://docs.x.com/developer-guidelines) and may lead to suspension or a permanent ban. Use it only if you accept that risk.

**How it works.** The Grok Bot cloud computer has a persistent browser: sessions are kept, and a login made in one bot is usable by others ([Use the computer and apps](https://docs.x.ai/grok-bot/computer-and-apps)). The Operator does not drive the page itself; it dispatches a computer-use subtask. Each bot runs one computer task at a time on its own screen.

**Step 1 — Log in once.** In your one-on-one chat with the Operator, open the computer view, take control, log in to X, complete 2FA, and tell the bot "done". Screen takeover is not available in group chats. The bot never types your password or asks for codes. If the session expires or asks for re-verification, the bot pauses and notifies you instead of trying to work around it.

**Step 2 — Trigger.** An hourly "posting check" routine (e.g. `CRON_TZ=<tz> 23 9-21 * * *`) handles only posts that are approved, due, and unmarked. Routines cannot log in for you. Breaking news can take a "fast lane": publish right after you approve.

**Step 3 — Subtask brief template:**
```text
In the cloud-computer browser, X is logged in as @<handle>.
If the browser is in use by another task (compose box half-open, page changing on its own), wait 2 minutes and check again.
1) Open https://x.com/<handle> and check recent posts. If a post starting with "<first 12 characters>" exists,
   do not post again; report its link only.
2) Open the compose box and type this body verbatim (Shift+Enter for line breaks, a blank line between paragraphs, no clipboard):
   <body>
3) For a quote post: open <original post URL> → Repost → Quote. Upload any image from <image path>.
4) Verify text, quote, and image. Do not click "Post" before <scheduled time>.
5) After posting, open the profile, get the new post's link, and save a screenshot of the post page to <queue folder>.
6) On any rate limit, captcha, account warning, lock, or login prompt, stop immediately, click nothing, and report what you saw.
Report: status, post link, final text, and whether you saw any warning.
```

**Step 4 — Receipt and log.** The subtask reports `done`, `blocked`, or `partial` with the link and final text. The Operator reads the post back with X's read-only search, switches the marker from `PUBLISHING_BY_<bot>` to `POSTED`, moves the folder to `published/`, appends a log line, and sends you the link.

**Step 5 — Failure handling:**

| Situation | Response |
|---|---|
| Subtask `blocked` (login, captcha) | Do not retry as-is; ask you to take control in a one-on-one chat |
| Page timeout or script error | Check the profile first to avoid double-posting |
| Two tasks want the same post | The `PUBLISHING_BY_<bot>` marker wins; the later one skips |
| Rate limit, captcha, warning, temporary label | Stop all automated posting and engagement for 24 hours, pause routines, log the risk event, notify you; twice in a week → wait for your decision |
| Session expired | Ask you to log in again; the bot never enters passwords |

**Six safeguards:** human cadence (1–3 originals a day, ≥3 hours apart, 1–4 minutes between replies, no on-the-hour bursts); low volume (no bulk likes or follows, no DMs, no profile edits); human review of every post; the "Automated" label if you go fully automated; no spam or reply-trading ([X Developer Policy](https://docs.x.com/developer-terms/policy)); log out of shared sessions when not needed ([Approvals](https://docs.x.ai/grok-bot/approvals-security-and-privacy)).

## 5. 30-day rollout plan

| Days | Goal | Key actions | Done when |
|---|---|---|---|
| 1–3 | Positioning & profile | One-line positioning, 3–5 pillars, three-part profile | A stranger can tell what you write about in 5 seconds |
| 2–5 | Build the team | Run `x-ops-team-setup`; connect the plugin; save style samples | You approve at least 3 of 5 trial drafts |
| 4–7 | Routines | Create schedules; test run all | 3 consecutive days of on-time output |
| 6–14 | Approval loop | Draft → approve → publish → link back | 100% complete logs |
| 8–20 | Replies | Private list; 3–5 substantive replies a day | Profile visits and follows from replies tracked |
| 10–20 | Format tests | Single, list, thread ×3 each; morning vs. afternoon | Weekly review compares relative ER |
| 15–21 | Browser posting (optional) | You log in; low-volume trial; rehearse the brake | All routines paused within 5 minutes |
| 21–28 | Double down | Expand the top 10% via 1-3-5 | New threads beat the median ER |
| 24–30 | Other-platform pilot | Drafts only | 3 drafts per platform, each with AI disclosure |
| 28–30 | Full review | Keep, cut, double down | Next 30-day plan written |

## 6. Adapting to other platforms

Reuse the research and review layers, not the publishing layer. Rewrite per platform instead of cross-posting. Several platforms require explicit AI-content disclosure — for example, Chinese regulations effective September 1, 2025 require users to declare AI-generated content ([CAC](https://www.cac.gov.cn/2025-03/14/c_1743654684782215.htm)), and Xiaohongshu may ban accounts run by AI hosting tools ([report](https://cbgc.scol.com.cn/news/7366379)). On such platforms, keep bots to research, drafts, and review; publish yourself in the official app.

## 7. Known gaps

- The X Automation Rules page could not be fetched (403); statements rely on the Developer Guidelines.
- Long-term ban probability for browser posting is unknown; the absence of warnings in limited use does not mean the platform permits it.
- Practitioner numbers (2–10×, 15–30 minutes, 10–20 replies a day) come from blogs, not controlled studies.
- Best-time studies conflict and mostly sample English-speaking audiences.
- The "first two hours" claim is an inference from a code parameter.
- The settings path for the "Automated" label and the reach impact of Premium were not verified on official pages.
