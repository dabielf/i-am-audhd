# i-am-audhd

An agent skill that shapes AI output for a reader who is autistic and has ADHD (AuDHD).

## What it changes

- **Literal wording.** No idioms, hidden requests, rhetorical questions, or vague "it" and "that".
- **One question at a time.** Several questions are announced by count, then asked one by one.
- **Answer first, reason attached.** The first line is the action or the answer, with one line of "why".
- **No silent changes.** Changes of plan, scope, assumption, or terminology are announced.
- **Honest uncertainty.** Facts, assumptions, and unknowns are labeled. No false confidence.
- **No scope creep.** The agent does what was asked, and asks before doing more.
- **Direct, not cold.** No cheerleading, no praise, no guessed feelings, no apology paragraphs.
- **Overview first, detail after.** Brevity without losing completeness.
- **Answers can just end.** No forced "next step".

It also resolves the places where autistic and ADHD needs conflict (brief vs complete, structure vs novelty, direction vs autonomy) instead of picking a side.

## Install

### Claude Code

Copy the skill folder into your skills directory:

```bash
git clone https://github.com/dabielf/i-am-audhd.git
cp -r i-am-audhd/skills/i-am-audhd ~/.claude/skills/
```

### Other agents

Copy `skills/i-am-audhd/SKILL.md` into the skills directory your agent uses, or paste its content into your custom instructions.

## Use

- The agent can load the skill on its own when you mention AuDHD or ask for literal, explicit communication.
- Load it yourself with `/i-am-audhd`.
- Once loaded, it stays on for the whole session.
- Turn it off with "stop audhd mode" or "normal mode".

## Acknowledgement

This skill exists because of [i-have-adhd](https://github.com/ayghri/i-have-adhd) by [Ayoub Ghriss](https://github.com/ayghri), a skill that stops coding agents from burying the answer.

`i-am-audhd` keeps its format (a few facts about how the reader reads, numbered rules, exceptions, and a pre-send check) and adapts the rules for readers who are both autistic and ADHD. Thank you, Ayoub.

## License

MIT
