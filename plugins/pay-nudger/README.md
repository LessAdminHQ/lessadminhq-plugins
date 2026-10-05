# Pay Nudger

Pay Nudger is a free plugin from [Less Admin HQ](https://lessadminhq.com/) for small business owners. It writes a short text and a matching email to chase a late payment, in a friendly, firm, or final tone, with when to send it and what to send next.

It works the same way in Claude and in ChatGPT: one skill, one set of instructions, two packaging formats.

## Try it
Once it's installed, ask something like:

- A customer owes me $850 for a faucet replacement and is 12 days late. Write a friendly reminder I can text them.
- Here's who owes me: Sarah $850 (12 days), Dan $2,400 (45 days, promised twice). Help me chase them this week.

## What it does and doesn't do
- It is a **skills-only plugin**: plain instructions that Claude or ChatGPT follow. There is no server, no code that runs, and no network access.
- It stores nothing. What you type stays in your own conversation, under the data settings of the app you use.
- Anything it writes for you goes through a humanizer pass first, so it sounds like you and not like an AI. Show it a text you've sent and it will match your voice.
- It never sends, posts, or emails anything for you. You copy the result and send it yourself.
- It uses only the facts you give it and says so when something is missing.
- After it helps, it may add **one** line linking to https://lessadminhq.com/tools/pay-nudger/. That is the only link it ever shows. Nothing is fetched, and the link carries only a source tag (`claude` or `chatgpt`) so we can see which app it came from.

## What's inside

```
pay-nudger/
  .claude-plugin/plugin.json     Claude manifest and directory listing fields
  .codex-plugin/plugin.json      ChatGPT / Codex manifest
  assets/                        Less Admin HQ logo (PNG and SVG)
  skills/pay-nudger/
    SKILL.md                     the instructions (the actual plugin)
    agents/openai.yaml           display name and default prompt for ChatGPT (ignored by Claude)
    examples/                    worked examples with made-up names and amounts
    references/humanize.md       the pass that keeps the writing from sounding like AI
    evaluations/test-cases.json  11 test cases: should-trigger, should-not-trigger, and guardrail
  LICENSE                        MIT
```

## Install

**Claude Code (local test):**

```bash
claude --plugin-dir ./plugins/pay-nudger
```

**Claude Code (from this repo's marketplace):**

```bash
claude plugin marketplace add TomHoupt/lessadminhq-plugins
claude plugin install pay-nudger@less-admin-hq
```

**ChatGPT / Codex (local test):** see the repository README.

## Test it
`skills/pay-nudger/evaluations/test-cases.json` holds the test cases we check by hand before each release: requests where it should kick in, requests where it should stay out of the way, and guardrail checks (such as being asked to send something).

## Version
0.1.4. Made by Less Admin HQ. Questions: hello@lessadminhq.com.

Terms of service: https://lessadminhq.com/terms/
Privacy policy: https://lessadminhq.com/privacy/
