---
name: reddit-voice
description: Converts polished, AI-sounding, or marketing-toned text into authentic, unpolished Reddit-native writing that reads as genuinely human and avoids getting buried by Reddit's hivemind. Use this whenever the user asks to "make this sound like Reddit," "humanize this for Reddit," "write this in Reddit style," "make this less AI," or asks for a Reddit post, and whenever converting a story, insight, stat, or promotional idea into something postable on Reddit. Also trigger for reviewing an existing draft Reddit post for "salesy," "AI slop," or "too polished" tells before it ships. Push to use this any time the destination is Reddit specifically — it is not a generic tone-softener, it encodes real behavioral rules about what gets a post buried vs. what survives.
---

# Reddit Voice

Converts text into writing that survives Reddit's specific hivemind, which downvotes two failure modes almost equally: AI-polished writing, and writing that is trying to sell something even subtly. The goal is a third lane — genuinely raw, first-person, lived-experience writing that a real Redditor would believe was typed in a hurry by a real person with nothing to sell.

This was reverse-engineered from ~30 real viral and non-viral Reddit posts (with engagement numbers) across r/ArtificialInteligence, r/AI_Agents, r/SaaS, r/marketing, r/b2bmarketing, r/gtmengineering, r/consulting, and r/Indian_flex, plus extensive user correction across many drafting rounds. Treat the rules below as load-bearing, not stylistic suggestions — several were only discovered by writing something that felt fine and having it rejected for a specific, nameable reason.

## The two failure modes to avoid

1. **AI slop / anti-AI doom** — polished sentence rhythm, "let's dive in," tidy conclusions, hedge-everything language, or content that's pure negativity/hype with no personal stake. Reddit hiveminds can smell AI-enhanced writing from a mile away and downvote it to oblivion.
2. **Salesy / snake oil, even subtly** — this is the harder failure mode and the one Claude defaults into without noticing. See "The sales-posture trap" below — it is about narrative *position*, not word choice, and no amount of softening the tone fixes it if the position is wrong.

## Core writing rules

1. **Never polish to perfection.** Don't clean up the rawness. Write like sending a WhatsApp or Slack message in a hurry: lowercase where it'd naturally happen, run-on sentences, weird or missing punctuation, the occasional loose grammar. Intentional imperfection reads as authentic; polish reads as corporate or AI-generated and gets torched.
2. **Structure it unstructured.** Don't connect every dot or fill every gap out of a worry that readers will be confused. Leave some holes on purpose. Comment-farmers who point out the gaps often end up boosting the post by starting an argument in the replies — that's a feature, not a risk to engineer away.
3. **Ground it in something that could actually happen.** Real-life texture, specific but not so specific it reads as checkable/fake. Keep most posts under ~200 words. A story can be stretched a little as long as it stays believable.
4. **End on an unresolved or discussion-baiting note, not a tidy conclusion.** Real posts often trail off ("anyway no real point to this just been thinking about it") or end with a genuine open question, not a thesis-wrapping final line. A post that "concludes itself" reads as constructed.
5. **Titles are one punchy declarative line**, not a stacked double-clause or colon-based headline. Should work almost like a question even when it's a statement — provocative enough that someone wants to argue with it. ("The AI Adoption gap is way more real than people think" — not "X: why Y actually means Z.")
6. **A numbered list needs ONE unifying thesis.** Every point should support the same underlying claim. A list that wanders across unrelated ideas (layoffs, weekends, conspiracies, pop culture) reads as unfocused rambling, not insight, no matter how raw the prose is.

## The sales-posture trap (read this before drafting anything client-related)

This is the single most common way a good idea gets ruined, and it is invisible in the sentence-level tone — it's about *where the narrator is standing*, not word choice.

**The tell:** any phrasing that puts the narrator in a sales-adjacent position — "prospect," "client," "discovery call," "case studies we sent," "what made them finally book a call," "was doing a paid audit for," "asked to see a founder's lead routing logic [in a professional capacity]." None of these are pitches. All of them quietly reposition the reader as someone who might be sold to next. Redditors detect this even without a link or CTA anywhere in the post.

**The fix is structural, not tonal.** Don't soften the language — remove the narrator from any position adjacent to a deal, a funnel, or a professional service relationship entirely. The narrator should be:
- a friend, sibling, cousin, coworker, neighbor, or stranger who told them something in a purely social context, OR
- the narrator themselves, describing their own first-hand experience with no "we sent them," "our client," or "the prospect" framing anywhere

**Also avoid:** any reference to having *read* something (comments, articles, threads) as the source of the insight. "Was reading through comments and noticed..." puts the narrator in a research/analyst posture, watching Reddit from outside it — which is its own version of the same tell. The insight should come from something the narrator lived or was told directly, not something they observed as a spectator.

**Never include:** a link, an explicit CTA, "click here," "check out," or any sentence that could be read as conditioning the reader toward a future pitch — even one that isn't there yet.

## Concrete over abstract — but not just "add a detail"

Early drafts that failed weren't vague — they had specific details, but details *manufactured to perfectly illustrate a thesis* (a dead Slack ping literally named "if_confused_ping_rohan," a doc literally named "TEMP" for a year). These still read as constructed once you look closely, because everything about them serves the point too neatly.

The real bar, learned from the best reference post (see `references/examples.md`): the insight should feel like a **byproduct of a real, slightly messy social moment**, not the point the moment was built to prove. The best real post has a whole preamble (hanging out, drinks, "hey bro vibe," ranting about AI being hype) that serves no thesis purpose at all — it's just what actually happened before the interesting part. Endings are often genuinely loose, not a "and that's when I realized X" wrap-up.

When drafting: don't start from the insight and build a scene to fit it. Try starting from an ordinary, slightly odd scene and let whatever's interesting fall out of it almost as an aside, sometimes only in the last line, sometimes not resolved at all.

## Register-matching by community

Different subreddits reward different emotional registers — check before writing if the destination sub is known:

- **Data/skeptic communities** (e.g., r/ArtificialInteligence): reward evidence-anchored reality checks — hard numbers, named real events. Punish pure assertion without evidence, and punish sci-fi/speculative framing (wrong register even if on-topic).
- **Builder/practitioner communities** (e.g., r/AI_Agents, r/gtmengineering): reward production war stories, technical specificity, definitional posts that draw a clean line between two commonly conflated things, first-person ownership of numbers ("I did X," not "a team I worked with did X").
- **Burnout/career communities** (e.g., r/marketing): reward confessional vulnerability and question-format titles over declarative statement titles. Self-implicating admissions ("I'm guilty of this too") defuse "who are you to talk" pushback before it happens — this move works across nearly every community, not just this one.
- **Practitioner-honesty communities** (e.g., r/b2bmarketing): reward named-and-shamed tactic callouts (without naming specific companies/people), rapid-fire tool-graveyard lists with a blunt one-line verdict each, and earned ambivalence over a tidy resolved answer.

If the destination sub is unknown, default to the general rules above and flag to the user that register may need adjusting once a sub is chosen.

## Kill list — if a draft has any of these, it needs a rewrite, not a polish pass

- A direct pitch, link, or CTA with no narrative wrapper around it
- A bare assertion or conclusion stated as fact with no evidence, number, or lived anecdote behind it
- Wrong emotional register for context (e.g., speculative/sci-fi framing in an evidence-driven community, or a "we're excited to announce" tone anywhere)
- The post becomes about itself — meta-commentary on karma, downvotes, mods, or "will this get removed" edits
- A numbered/listicle post with no single unifying thesis tying every point together
- Any sales-posture language per the section above, even without an explicit pitch

## Workflow

1. Get the source material — the raw fact, number, story, or draft the user wants converted.
2. Identify which failure mode the current draft is closest to (if revising): AI-polish, sales-posture, or manufactured-specificity. Name it explicitly when explaining the fix — this helps the user calibrate faster than a generic "make it more real" note.
3. Draft in the raw voice per the rules above. Titles as a single punchy line, offered as options if the user wants to pick — don't assume the title is locked.
4. If a destination subreddit is known, apply register-matching.
5. Read the draft back against the kill list before presenting it.
6. Present drafts as options, not a final answer — this is a subjective, taste-driven craft the user is directing. Expect and invite correction on specific lines rather than treating a first draft as done.

See `references/examples.md` for the full annotated reference post and before/after examples of common fixes (sales-posture removal, manufactured-detail removal, ownership-voice tightening).
