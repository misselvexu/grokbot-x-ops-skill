# Contributing

**English** | [简体中文](CONTRIBUTING.zh-CN.md)

Thank you for helping improve this project. By participating, you agree to follow our [Code of Conduct](CODE_OF_CONDUCT.md).

## Ways to contribute

- **Report a bug** — a step in the skill that fails, is unclear, or no longer matches the product. Use the [bug report form](https://github.com/misselvexu/grokbot-x-ops-skill/issues/new?template=bug_report.yml).
- **Suggest an improvement** — a new guardrail, a better routine, a platform adaptation. Use the [feature request form](https://github.com/misselvexu/grokbot-x-ops-skill/issues/new?template=feature_request.yml).
- **Improve docs or translations** — clarity fixes and translation corrections are always welcome.
- **Submit a pull request** — see the guidelines below.

## Ground rules

1. **Bilingual parity is required.** Every change to the skill or docs must update both English and Simplified Chinese. In `SKILL.md`, English comes first within each section, followed by Chinese, and both must describe the same steps.
2. **No fabrication.** Every factual claim about X, Grok Bot, or a platform rule must link to a public source. Mark inferences explicitly as inferences.
3. **Safety first.** Changes must not weaken the default guardrails: human approval by default, no credential handling by bots, low volume, and the automatic risk brake. Proposals that increase automation must explain the risk and keep it opt-in.
4. **No private data.** Never include real account handles (other than placeholders like `@<handle>`), personal information, API keys, tokens, cookies, or screenshots of private accounts.
5. **Keep placeholders generic.** Use `<workdir>`, `<tz>`, `<handle>`, and similar placeholders instead of real values.

## Pull request process

1. Fork the repository and create a branch: `git checkout -b docs/clarify-step-5`.
2. Make your change in both languages.
3. Update `CHANGELOG.md` under `[Unreleased]`.
4. Open a pull request and complete the checklist in the template.
5. A maintainer will review it. Small, focused pull requests are reviewed fastest.

## Style

- English: plain, direct, imperative voice for instructions ("Ask the owner…", "Do not…").
- Chinese: concise Simplified Chinese; keep product terms such as skill, routine, Test run, and Connect apps as they appear in the product UI.
- Markdown: one sentence per bullet where possible; tables for structured comparisons.

## Security

Do not report security issues in public issues. See [SECURITY.md](SECURITY.md).
