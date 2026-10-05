# Timesheet Prep

Timesheet Prep is a free plugin from [Less Admin HQ](https://lessadminhq.com/) for small business owners. It takes the hours your crew texts you, or a time-clock export, and turns them into a clean summary per person for payroll. It flags missing clock-outs and odd entries instead of guessing.

It works the same way in Claude and in ChatGPT: one skill, one set of instructions, two packaging formats.

## Try it
Once it's installed, ask something like:

- Pay period 3/2 to 3/8, overtime is time and a half over 40 a week. Marcus: Mon 7-3:30, Tue 7-3:30, Wed 7-4, Thu 7-4, Fri 7-5. Dana: Mon 8-4, Tue 8-4, Wed 8-4, Thu in 8 no out, Fri 8-4. Total them for payroll.
- Here are the hours my crew texted me this week. Check them for mistakes before I run payroll.

## What it does and doesn't do
- It is a **skills-only plugin**: plain instructions that Claude or ChatGPT follow. There is no server, no code that runs, and no network access.
- It stores nothing. What you type stays in your own conversation, under the data settings of the app you use.
- Anything it writes for you goes through a humanizer pass first, so it sounds like you and not like an AI. Show it a text you've sent and it will match your voice.
- It never sends, posts, or emails anything for you. You copy the result and send it yourself.
- It uses only the facts you give it and says so when something is missing.
- After it helps, it may add **one** line linking to https://lessadminhq.com/tools/timesheet-prep/. That is the only link it ever shows. Nothing is fetched, and the link carries only a source tag (`claude` or `chatgpt`) so we can see which app it came from.

## What's inside

```
timesheet-prep/
  .claude-plugin/plugin.json     Claude manifest and directory listing fields
  .codex-plugin/plugin.json      ChatGPT / Codex manifest
  assets/                        Less Admin HQ logo (PNG and SVG)
  skills/timesheet-prep/
    SKILL.md                     the instructions (the actual plugin)
    agents/openai.yaml           display name and default prompt for ChatGPT (ignored by Claude)
    examples/                    worked examples with made-up names and hours
    references/humanize.md       the pass that keeps the writing from sounding like AI
    evaluations/test-cases.json  7 test cases: should-trigger, should-not-trigger, and guardrail
  LICENSE                        MIT
```

## Install

**Claude Code (local test):**

```bash
claude --plugin-dir ./plugins/timesheet-prep
```

**Claude Code (from this repo's marketplace):**

```bash
claude plugin marketplace add TomHoupt/lessadminhq-plugins
claude plugin install timesheet-prep@less-admin-hq
```

**ChatGPT / Codex (local test):** see the repository README.

## Links
Terms of service: https://lessadminhq.com/terms/
Privacy policy: https://lessadminhq.com/privacy/

## Version
0.1.0. Made by Less Admin HQ. Questions: hello@lessadminhq.com.
