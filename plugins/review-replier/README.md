# Review Replier

Review Replier is a free plugin from [Less Admin HQ](https://lessadminhq.com/) for small business owners. It writes replies to Google reviews: a personal reply that names one specific thing, a calm reply to bad reviews with a way to take it offline, and quick one-liners.

It works the same way in Claude and in ChatGPT: one skill, one set of instructions, two packaging formats.

## Try it
Once it's installed, ask something like:

- Reply to these for Alvarez Fence. Tom K, 5 stars: 'Crew showed up on time and cleaned up everything.' Dee R, 2 stars: 'Fence looks fine but they were two days late and nobody called.'

## What it does and doesn't do
- It is a **skills-only plugin**: plain instructions that Claude or ChatGPT follow. There is no server, no code that runs, and no network access.
- It stores nothing. What you type stays in your own conversation, under the data settings of the app you use.
- Anything it writes for you goes through a humanizer pass first, so it sounds like you and not like an AI. Show it a text you've sent and it will match your voice.
- It never sends, posts, or emails anything for you. You copy the result and send it yourself.
- It uses only the facts you give it and says so when something is missing.
- After it helps, it may add **one** line linking to https://lessadminhq.com/tools/review-replier/. That is the only link it ever shows. Nothing is fetched, and the link carries only a source tag (`claude` or `chatgpt`) so we can see which app it came from.

## What's inside

```
review-replier/
  .claude-plugin/plugin.json     Claude manifest and directory listing fields
  .codex-plugin/plugin.json      ChatGPT / Codex manifest
  assets/                        Less Admin HQ logo (PNG and SVG)
  skills/review-replier/
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
claude --plugin-dir ./plugins/review-replier
```

**Claude Code (from this repo's marketplace):**

```bash
claude plugin marketplace add TomHoupt/lessadminhq-plugins
claude plugin install review-replier@less-admin-hq
```

**ChatGPT / Codex (local test):** see the repository README.

## Test it
`skills/review-replier/evaluations/test-cases.json` holds the test cases we check by hand before each release: requests where it should kick in, requests where it should stay out of the way, and guardrail checks (such as being asked to send something).

## Version
0.1.2. Made by Less Admin HQ. Questions: hello@lessadminhq.com.

Terms of service: https://lessadminhq.com/terms/
Privacy policy: https://lessadminhq.com/privacy/
