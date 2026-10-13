# reddit-voice

A Claude skill that turns polished, AI-sounding or salesy text into raw, human Reddit posts that don't get downvoted.

## Why this exists

Ask any AI to "write a Reddit post" and you get something that dies at 0 upvotes. You get clean sentences, a tidy conclusion and a little "what do you think?" at the end. Redditors spot it right away.

Telling the AI to "make it sound more casual" doesn't fix it either. You end up with the same post in lowercase.

This skill came out of trying to work out *why* those posts fail, as specifically as possible, and then writing those reasons down as rules Claude can follow.

## How it was built

It wasn't written from opinion. The process was:

1. **Collected ~30 real Reddit posts**, both viral and ones that flopped, along with their engagement numbers. They came from:
   - r/ArtificialInteligence
   - r/AI_Agents
   - r/SaaS
   - r/marketing
   - r/b2bmarketing
   - r/gtmengineering
   - r/consulting
   - r/Indian_flex
2. **Compared what the winners had in common** and what the losers got wrong.
3. **Drafted posts over many rounds and rejected the ones that failed**, each time for a specific reason that could be named. A lot of the rules below only showed up because a draft *felt* fine and was still wrong.
4. **Wrote every lesson into the skill** so it doesn't make the same mistake again.

## What the research found

### Reddit punishes two things almost equally

1. **AI slop.** Smooth rhythm, "let's dive in", hedging everything, neat wrap-ups. It also covers pure hype or pure doom with no personal stake behind it.
2. **Selling, even subtly.** This was the bigger discovery, and it's the one AI falls into without noticing.

The skill aims for a third lane: raw, first-person, lived experience from someone who obviously has nothing to sell.

### The "sales posture" trap

This is the most important finding in the whole skill.

A post can contain no link, no pitch and no call to action and *still* read as an ad. Words like "prospect", "client", "discovery call" or "case studies we sent" quietly put the writer in a seller's seat, and readers pick up on it.

**Softening the tone doesn't fix this. Changing where the narrator is standing does.**

| Fails | Works |
|---|---|
| "was in a discovery call and the prospect asked me if the AI thing was a chatbot..." | "my uncle runs a distribution business and called me asking if he should be worried about the AI thing..." |

The facts are almost identical. Only the narrator's position changed, from salesperson to family member.

The same thing applies to "I was reading comments and noticed...". That puts the writer in an analyst's seat, watching from outside. Things you lived or were told directly work better.

### Fake-specific details also get caught

"Add concrete details" is common advice, and it backfires when the detail is *too* perfect. A Slack bot literally named `if_confused_ping_rohan` was rejected for exactly this reason. It was clearly invented to prove the point.

What works is a detail that falls out of a messy, ordinary moment. Real posts have boring setup, loose ends and endings that never fully land.

### Every subreddit wants a different mood

| Type of sub | What wins |
|---|---|
| Data / skeptic (r/ArtificialInteligence) | Hard numbers and real events. No hype, no sci-fi. |
| Builders (r/AI_Agents, r/gtmengineering) | War stories, technical detail, owning your numbers ("I did X") |
| Career / burnout (r/marketing) | Confessions, admitting your own guilt, question-style titles |
| Honest practitioners (r/b2bmarketing) | Calling out tactics, blunt tool verdicts, mixed feelings over neat answers |

### Small rules that matter

- Keep most posts under ~200 words
- Titles are one punchy line, with no colon and no two-part headline
- A numbered list needs one single idea tying every point together
- End loose or on an open question, never with a neat "and that's when I realized..."
- Leave gaps on purpose. People arguing about them in the comments boosts the post.

## The benchmark post

The whole skill is measured against one real post, *"The AI Adoption gap is way more real than people think"*. Here's why it works:

- It opens with drinks with a founder who turned into a "hey bro" friend. Nothing about it reads as professional or sales.
- The narrator starts out **anti-AI** and ranting, which isn't the voice of someone who's selling.
- Half the post is setup that doesn't serve any point. That's just what happened.
- The payoff is oddly specific and slightly embarrassing: a JBL department head asking for help making a WhatsApp broadcast channel for his wife. Nobody would bother making that up.
- It ends on one loose thought ("AI is being sold to the wrong people") and doesn't try to wrap everything up.

The full post and annotations are in [`references/examples.md`](reddit-voice/references/examples.md).

## Why it's different from other "humanizer" tools

Most humanizers work at the **word level**. They swap vocabulary, break up sentences and remove em dashes.

This skill works at the **position level**:

- **Who is the narrator?** A friend, a sibling, someone who lived it, and never a seller or an analyst.
- **Where did the insight come from?** A real moment, not something designed backwards from the point.
- **Which subreddit is it for?** The mood changes for each community.
- **Does it pass the kill list?** Any one hit means a rewrite, not a polish.

It also explains *why* a draft fails (AI polish, sales posture or manufactured detail), so you learn to see it yourself.

## The kill list

If a draft has any of these, it gets rewritten:

- A pitch, link or CTA with no story around it
- A big claim with no number, evidence or personal anecdote behind it
- The wrong mood for the sub, e.g. sci-fi framing in a data sub, or "we're excited to announce" anywhere
- The post being about itself: karma, mods, "will this get removed"
- A list with no single point tying it together
- Any sales-posture language, even with no actual pitch

## What's inside

```
reddit-voice/
  SKILL.md                 # the rules, kill list and workflow Claude follows
  references/examples.md   # benchmark post + before/after fixes
```

## Install

**Claude Code:** copy the `reddit-voice` folder into `~/.claude/skills/`.

```bash
git clone https://github.com/siddheshpatankar786-commits/reddit-voice-skill.git
cp -r reddit-voice-skill/reddit-voice ~/.claude/skills/
```

**claude.ai:** zip the `reddit-voice` folder and upload it under Settings > Capabilities > Skills.

## How to use it

Just ask Claude things like:

- "write a reddit post about ..."
- "make this sound like reddit"
- "is this draft too salesy for r/SaaS?"

Tell it which subreddit you're posting in if you know, so it can match the mood. It gives you drafts as options, so push back on specific lines. That's how it's meant to work.
