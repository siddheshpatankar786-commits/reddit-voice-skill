# reddit-voice

A Claude skill that turns polished, AI-sounding, or salesy text into raw, Reddit-native writing that doesn't get buried.

It's built from ~30 real viral and non-viral Reddit posts plus a lot of drafting rounds. It covers the two things Reddit downvotes hardest: AI-polished prose and subtle sales posture.

## What's inside

```
reddit-voice/
  SKILL.md                 # the rules, kill list, workflow
  references/examples.md   # benchmark post + before/after fixes
```

## Install

**Claude Code:** copy the `reddit-voice` folder into `~/.claude/skills/`.

```bash
git clone <this-repo-url>
cp -r reddit-voice-skill/reddit-voice ~/.claude/skills/
```

**claude.ai:** zip the `reddit-voice` folder and upload it under Settings > Capabilities > Skills.

## Use

Ask Claude for a Reddit post, or to "make this sound like Reddit", and the skill kicks in. Tell it the target subreddit if you know it so it can match the register.
