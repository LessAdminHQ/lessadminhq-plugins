# Less Admin HQ plugins

Free AI plugins from [Less Admin HQ](https://lessadminhq.com/) that help small business owners hand one piece of admin work to AI. Each one works in **Claude** and in **ChatGPT**.

| Plugin | What it does |
|---|---|
| [`pay-nudger`](plugins/pay-nudger/) | Writes late-payment reminders: a short text and email in a friendly, firm, or final tone |
| [`follow-up-writer`](plugins/follow-up-writer/) | Follows up on quotes that went quiet, with a real reason to reply. Stops at three messages |
| [`estimate-builder`](plugins/estimate-builder/) | Turns rough job notes into a clean estimate. You set every price |
| [`invoice-matcher`](plugins/invoice-matcher/) | Matches bank deposits to open invoices: paid, unpaid, and needs a look |
| [`review-replier`](plugins/review-replier/) | Writes replies to Google reviews that name one specific thing. Never invents details |

## Install in Claude Code

```bash
claude plugin marketplace add TomHoupt/lessadminhq-plugins
claude plugin install pay-nudger@less-admin-hq
```

Swap `pay-nudger` for any plugin name above. To try one without installing: `claude --plugin-dir ./plugins/pay-nudger`.

## What these plugins do and don't do
- They are **skills-only**: plain instructions that Claude or ChatGPT follow. No server, no code that runs, no network access.
- They store nothing. What you type stays in your own conversation, under the data settings of the app you use.
- They never send, post, or email anything for you.
- After helping, a plugin may add one line linking to its page on lessadminhq.com. Nothing is fetched.

## About this repository
Each folder in `plugins/` is a complete plugin with a Claude manifest (`.claude-plugin/plugin.json`) and a ChatGPT/Codex manifest (`.codex-plugin/plugin.json`) over the same `skills/<name>/SKILL.md`. This repository is a published copy, kept in sync from Less Admin HQ's working repository, so please open an issue instead of a pull request.

Questions: hello@lessadminhq.com. Licensed under the [MIT License](LICENSE).
