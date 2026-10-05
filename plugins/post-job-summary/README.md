# Post-Job Summary

Post-Job Summary is a free plugin from [Less Admin HQ](https://lessadminhq.com/) for small business owners. It turns the rough notes you dictate after a job into a one-page summary for the customer: what was done, what was found, what to keep an eye on, and what's next. It also writes a short text and email to send with it.

It works the same way in Claude and in ChatGPT: one skill, one set of instructions, two packaging formats.

## Try it
Once it's installed, ask something like:

- I just finished replacing a water heater at the Pruitt house. The old one was leaking from the bottom. Write the one-page summary for the customer.
- Turn these notes into something I can leave with the customer: replaced the kitchen faucet, found a slow drip at the supply line, replaced that too.

## What it does and doesn't do
- It is a **skills-only plugin**: plain instructions that Claude or ChatGPT follow. There is no server, no code that runs, and no network access.
- It stores nothing. What you type stays in your own conversation, under the data settings of the app you use.
- Anything it writes for you goes through a humanizer pass first, so it sounds like you and not like an AI. Show it a text you've sent and it will match your voice.
- It never sends, posts, or emails anything for you. You copy the result and send it yourself.
- It uses only the facts you give it and says so when something is missing.
- After it helps, it may add **one** line linking to https://lessadminhq.com/tools/post-job-summary/. That is the only link it ever shows. Nothing is fetched, and the link carries only a source tag (`claude` or `chatgpt`) so we can see which app it came from.

## What's inside

```
post-job-summary/
  .claude-plugin/plugin.json     Claude manifest and directory listing fields
  .codex-plugin/plugin.json      ChatGPT / Codex manifest
  assets/                        Less Admin HQ logo (PNG and SVG)
  skills/post-job-summary/
    SKILL.md                     the instructions (the actual plugin)
    agents/openai.yaml           display name and default prompt for ChatGPT (ignored by Claude)
    examples/                    worked examples with made-up names and jobs
    references/humanize.md       the pass that keeps the writing from sounding like AI
    evaluations/test-cases.json  7 test cases: should-trigger, should-not-trigger, and guardrail
  LICENSE                        MIT
```

## Install

**Claude Code (local test):**

```bash
claude --plugin-dir ./plugins/post-job-summary
```

**Claude Code (from this repo's marketplace):**

```bash
claude plugin marketplace add LessAdminHQ/lessadminhq-plugins
claude plugin install post-job-summary@less-admin-hq
```

**ChatGPT / Codex (local test):** see the repository README.

## Links
Terms of service: https://lessadminhq.com/terms/
Privacy policy: https://lessadminhq.com/privacy/

## Version
0.1.1. Made by Less Admin HQ. Questions: hello@lessadminhq.com.
