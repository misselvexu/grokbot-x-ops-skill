<div align="center">

# Grok Bot X Ops Skill

**Turn your Grok Bot into a small, human-supervised editorial team for your X account — set up in one message.**

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)](CHANGELOG.md)
[![Language](https://img.shields.io/badge/language-EN%20%7C%20%E4%B8%AD%E6%96%87-orange.svg)](README.zh-CN.md)
[![Skill](https://img.shields.io/badge/skill-x--ops--team--setup-6f42c1.svg)](skills/x-ops-team-setup/SKILL.md)

**English** | [简体中文](README.zh-CN.md)

![Cover](assets/cover.jpg)

</div>

## Table of Contents

- [Overview](#overview)
- [Quick Start (one-click)](#quick-start-one-click)
- [What It Builds](#what-it-builds)
- [Architecture](#architecture)
- [Safety & Guardrails](#safety--guardrails)
- [Methodology Highlights](#methodology-highlights)
- [Docs](#docs)
- [FAQ](#faq)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Disclaimer](#disclaimer)

## Overview

`x-ops-team-setup` is a single, self-contained, bilingual (English / 简体中文) skill file for [Grok Bot](https://docs.x.ai/grok-bot/bots). Hand it to your main bot and it walks you through a short setup interview, then builds a complete X (Twitter) operations team: dedicated bots, reusable skills, scheduled routines, and a **draft → approve → publish** workflow.

The design principle is simple: **automate the preparation, not the judgment.** Bots research, verify, draft, and analyze on a schedule; you decide what goes out.

## Quick Start (one-click)

Send this message to your main Grok Bot:

```text
Read https://raw.githubusercontent.com/misselvexu/grokbot-x-ops-skill/main/skills/x-ops-team-setup/SKILL.md, save it as a skill, then run it with me.
```

Your bot will then:

1. Ask nine setup questions, one at a time (account, time zone, positioning and content pillars, language, cadence, approval mode, optional browser posting, engagement caps, style samples). Say "skip" to accept a default.
2. Connect the X plugin through its own Connect authorization — it never asks for your password, 2FA code, or tokens.
3. Propose a bot roster, create it after you approve, save three skills, and set up routines.
4. Test run every routine, then send you a summary of everything it built and every default it used.

> **Prerequisites:** a Grok Bot account and an X account you own. Browser-based posting is **off by default**.

## What It Builds

| Component | Details |
|---|---|
| **Bots (3–6)** | **Researcher** (optionally split by source: GitHub, papers, news/trending) — finds and verifies material. **Operator** — drafts posts and first replies, schedules them, runs approvals, publishes and logs when allowed. **Growth Analyst** — read-only benchmarking, daily topic hints, weekly review. |
| **Skills** | `x-material-scout` (gather & verify), `x-draft-and-publish` (draft, approve, publish, log), `x-growth-review` (relative-ER review). |
| **Routines** | Weekday schedules pinned with `CRON_TZ`, off-the-hour minutes, ≥5 minutes apart, test-run before going live. |
| **Approval flow** | File-based queue (`queue/YYYY-MM-DD/NN_slug/`) with `main.txt`, `first_reply.txt`, `note.txt`; approvals in a one-on-one chat; replies "post", "edit: …", or "drop"; append-only publish log. |
| **Cloud-browser posting (optional)** | You log in once yourself; an hourly routine publishes only approved, due posts via a computer-use subtask, with duplicate checks, screenshot receipts, and an automatic 24-hour stop on any risk signal. |

## Architecture

![Multi-bot team: Researchers, Growth Analyst, and Operator](assets/architecture-team.jpg)

*Figure 1. Read-only bots (Researcher, Growth Analyst) feed the Operator, the only bot that touches the account.*

![Content pipeline: material → draft → approval → publish → review](assets/content-pipeline.jpg)

*Figure 2. The content pipeline. The Growth Analyst's reviews loop back into topic selection.*

Design principles:

1. **Single owner per stage** — each stage belongs to exactly one bot.
2. **File-based handoffs** — pass only "path + three-sentence summary + next owner".
3. **Separate read and write layers** — only the Operator can act on the account.
4. **Closed loop** — weekly reviews feed the next week's topics.

## Safety & Guardrails

> [!WARNING]
> X's [Developer Guidelines](https://docs.x.com/developer-guidelines) list automation outside the official API — including browser scripts — as behavior that can lead to suspension or a permanent ban. If you enable browser-based posting, you accept that risk.

Built-in guardrails:

- **Human approval by default.** No post, reply, like, follow, or DM goes out without your approval unless you explicitly define an autonomous scope.
- **No credentials in chat.** The bot never asks for or types your password, 2FA code, API key, or token. You log in yourself via screen takeover.
- **Low volume, human cadence.** 1–3 originals per day, ≥3 hours apart; 1–4 minutes between replies; at most one reply per author per day; sparing likes; no bulk follows; no DMs; no profile edits.
- **Automatic brake.** Any rate limit, captcha, warning, or temporary label stops all automated posting and engagement for 24 hours and pauses routines. Two incidents in one week hand the decision back to you.
- **Disclosure.** Fully automated accounts without human review should enable X's "Automated" label.
- **No spam.** No duplicate content, no paid engagement, no reply-trading groups ([X Developer Policy](https://docs.x.com/developer-terms/policy)).
- **Credential hygiene.** Browser sessions on the shared cloud computer are usable by every bot on your account; log out when you no longer need them ([Approvals, security, and privacy](https://docs.x.ai/grok-bot/approvals-security-and-privacy)).

![Cloud-browser posting with persistent login, verbatim typing, screenshot receipts, and a risk brake](assets/cloud-browser-posting.jpg)

*Figure 3. Optional cloud-browser posting with guardrails.*

## Methodology Highlights

The skill encodes practices from public, traceable sources. These are practitioner experience, not platform rules — validate them with your own data. See [docs/methodology.md](docs/methodology.md) for the full write-up.

- **Profile in one line:** who you are, what you write about, and why someone should follow you — [Justin Welsh](https://justinwelsh.me/essays/5-000-twitter-followers-90-days-1-guide).
- **Content matrix:** cross sub-topics with 5–7 post styles to generate 75–100 ideas — [Justin Welsh](https://justinwelsh.me/essays/build-a-content-library).
- **Hooks:** the first line has two jobs — stop the scroll and earn the click — [Ship 30 for 30](https://www.ship30for30.com/post/how-to-write-viral-twitter-thread-hooks-with-6-clear-examples).
- **Replies:** target same-niche accounts 2–10× your size within 15–30 minutes of posting, and always add something new — [ClimbX](https://climbx.so/blog/twitter-reply-guy-strategy).
- **Write for shares and replies:** in X's open-source ranker, a copy-link share weighs 20, a reply 5, a like 0.66, and a report −234 (weights multiply predicted probabilities) — [param.rs](https://github.com/xai-org/x-algorithm/blob/main/home-mixer/params/param.rs).
- **Avoid AI slop:** X revoked API access for "infofi" apps over AI-generated filler and reply spam — [Nikita Bier](https://x.com/nikitabier/status/2011825522817270230).

## Docs

| Document | Description |
|---|---|
| [`skills/x-ops-team-setup/SKILL.md`](skills/x-ops-team-setup/SKILL.md) | The bilingual skill itself |
| [`docs/methodology.md`](docs/methodology.md) · [中文](docs/methodology.zh-CN.md) | Methods, algorithm weights, cloud-browser tutorial, 30-day plan |
| [`CHANGELOG.md`](CHANGELOG.md) | Release history |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) · [中文](CONTRIBUTING.zh-CN.md) | How to contribute |
| [`SECURITY.md`](SECURITY.md) | How to report security issues privately |

## FAQ

**Can the X plugin post for me?**
No. The Grok Bot X plugin can read timelines, mentions, bookmarks, lists, search, and trends, but does not currently support posting. You can post yourself, use the official X API or a scheduler built on it, or enable the optional cloud-browser flow.

**Will this get my account banned?**
If you publish bot-prepared drafts yourself, no non-API automation is involved. Browser-based posting is non-API automation under X's rules and carries real risk; the skill keeps it off by default and wraps it in guardrails, but cannot eliminate the risk.

**Does the bot ever see my password?**
No. You log in to X yourself in the cloud browser via screen takeover in a one-on-one chat. The bot is instructed never to request or type credentials.

**Can I use it for other platforms?**
The research, drafting, and review layers transfer well. Publishing rules differ by platform, and several require explicit AI-content disclosure; keep bots to research, drafts, and review there. See the methodology doc.

**How do I stop everything?**
Pause routines from the Routines list in each bot's info panel, or say "Stop now" in a chat to halt the current task (completed actions are not undone).

**What is shared when someone replicates this?**
Only the skill text in this repository. Your accounts, logins, computer, and chat history are never included.

## Roadmap

- [ ] Example `settings.md`, `style.md`, and `donts.md` templates
- [ ] Optional skill variant for posting via the official X API
- [ ] Platform-specific adaptation guides (drafts-only workflows)
- [ ] Sample weekly review report format

Suggestions are welcome via [feature requests](https://github.com/misselvexu/grokbot-x-ops-skill/issues/new/choose).

## Contributing

Contributions are welcome — please read [CONTRIBUTING.md](CONTRIBUTING.md) and our [Code of Conduct](CODE_OF_CONDUCT.md). Every change to the skill or docs must keep the English and Chinese versions in sync.

## License

Released under the [MIT License](LICENSE). © 2026 misselvexu.

## Disclaimer

This is an independent community project. It is **not affiliated with, endorsed by, or sponsored by X Corp. or the makers of Grok Bot**. Product names are used for identification only. Platform features and rules change; you are responsible for complying with the [X Developer Guidelines](https://docs.x.com/developer-guidelines), the [X Developer Policy](https://docs.x.com/developer-terms/policy), X's platform rules, and the terms of any platform you use. Nothing here is legal advice.
