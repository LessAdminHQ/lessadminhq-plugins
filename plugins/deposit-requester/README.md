# Deposit Requester

Deposit Requester is a free plugin from [Less Admin HQ](https://lessadminhq.com/) for small business owners. After a customer says yes, it writes a short text and a matching email asking for a deposit, a confirmation to send once it's paid, and, if you want, a short deposit policy for your booking page.

It works the same way in Claude and in ChatGPT: one skill, one set of instructions, two packaging formats.

## Try it
Once it's installed, ask something like:

- Rob accepted my $2,580 fence estimate. I want 20% down to hold the 14th. Write the deposit request.
- A customer booked a Saturday photo shoot. I want a $150 deposit to hold the date. Write the text and the confirmation for when it's paid.

## What it does and doesn't do
- It is a **skills-only plugin**: plain instructions that Claude or ChatGPT follow. There is no server, no code that runs, and no network access.
- It stores nothing. What you type stays in your own conversation, under the data settings of the app you use.
- Anything it writes for you goes through a humanizer pass first, so it sounds like you and not like an AI. Show it a text you've sent and it will match your voice.
- It never sends, posts, or emails anything for you. You copy the result and send it yourself.
- It uses only the facts you give it and says so when something is missing.
- After it helps, it may add **one** line linking to https://lessadminhq.com/tools/deposit-requester/. That is the only link it ever shows. Nothing is fetched, and the link carries only a source tag (`claude` or `chatgpt`) so we can see which app it came from.

## What's inside

```
deposit-requester/
  .claude-plugin/plugin.json     Claude manifest and directory listing fields
  .codex-plugin/plugin.json      ChatGPT / Codex manifest
  assets/                        Less Admin HQ logo (PNG and SVG)
  skills/deposit-requester/
    SKILL.md                     the instructions (the actual plugin)
    agents/openai.yaml           display name and default prompt for ChatGPT (ignored by Claude)
    examples/                    worked examples with made-up names and amounts
    references/humanize.md       the pass that keeps the writing from sounding like AI
    evaluations/test-cases.json  7 test cases: should-trigger, should-not-trigger, and guardrail
  LICENSE                        MIT
```

## Install

**Claude Code (local test):**

```bash
claude --plugin-dir ./plugins/deposit-requester
```

**Claude Code (from this repo's marketplace):**

```bash
claude plugin marketplace add TomHoupt/lessadminhq-plugins
claude plugin install deposit-requester@less-admin-hq
```

**ChatGPT / Codex (local test):** see the repository README.

## Links
Terms of service: https://lessadminhq.com/terms/
Privacy policy: https://lessadminhq.com/privacy/

## Version
0.1.0. Made by Less Admin HQ. Questions: hello@lessadminhq.com.
