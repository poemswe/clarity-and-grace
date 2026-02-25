# Clarity and Grace

This Claude Code plugin teaches Claude to write clear, concrete prose.

## What it does

The plugin applies a three-layer writing system whenever Claude writes or edits text that humans will read. That includes documentation, commit messages, error messages, READMEs, reports, UI copy, and explanations.

The three layers draw from four books.

1. **Stance** from Thomas & Turner's *Clear and Simple as the Truth*. Write as if pointing something out to an intellectual equal. The motive is truth. The tone is conversational.

2. **Cognition** from Pinker's *The Sense of Style*. Fight the curse of knowledge. Start from what the reader already knows. Keep working memory load under four items per sentence.

3. **Mechanics** from Strunk's *Elements of Style* and Williams' *Style: Clarity and Grace*. Write in active voice and positive form. Use specific language. Make characters the subject and actions the verb. Put old information before new and emphatic words at the end.

The plugin ships four condensed reference files with before/after examples for every rule. A separate AI slop ban list cites the principle behind every category.

| File | Covers |
|---|---|
| `strunk-condensed.md` | Active voice, positive form, concrete language, needless words, parallel construction, emphasis |
| `williams-condensed.md` | Characters as subjects, actions as verbs, old-before-new, topic strings, stress position, concision, coherence, elegance |
| `pinker-condensed.md` | Meta-commentary bans, hedging bans, curse of knowledge, classic prose stance |
| `ai-slop.md` | Banned vocabulary (Liang et al. 2024), filler phrases, engagement bait, thought-leadership slop, LinkedIn modifiers, formulaic structures |

## Example

**Before (standard AI output)**

> We hit 100K ARR with zero paid ads. Here's how. It wasn't magic and it wasn't luck. It was eighteen months of relentless focus on three things. First, we built in public. Every win, every failure, every pivot was shared openly. People followed the journey and became customers because they felt invested in our story. Second, we made our free tier genuinely useful. Not a stripped-down demo. A real product that solved a real problem. Users who got value for free became our best evangelists. Third, we obsessed over customer feedback. Every feature request, every bug report, every churned user got a personal response. That's it. No growth hacks. No viral loops. No secret sauce. Just consistent execution on fundamentals.

**After (with clarity-and-grace plugin)**

> We reached $100K ARR without paid ads. We focused on three things for eighteen months.
>
> We built in public and shared every win, failure, and pivot. People followed the progress and became customers because they felt invested.
>
> We made our free tier a standalone product that solves a real problem. Users who got genuine value became our best evangelists.
>
> We answered every feature request, bug report, and churn email personally.
>
> We executed three fundamentals consistently. That was the whole strategy.

**What changed**

| Before | After | Rule |
|---|---|---|
| "Here's how" | Cut | AI slop, thought-leadership. Also Williams 7, concision. |
| "It wasn't magic and it wasn't luck" | Cut | Strunk 11, positive form. Say what IS. |
| "It was eighteen months of relentless focus" | "We focused on three things for eighteen months" | Williams 1, characters as subjects. "We" replaces empty "it was." |
| "relentless focus" | "focus" | AI slop, LinkedIn modifiers. Performative adverb adds nothing. |
| "Every win, every failure, every pivot was shared openly" | "shared every win, failure, and pivot" | Strunk 10, active voice. |
| "followed the journey" | "followed the progress" | AI slop, banned vocabulary. "Journey" is a machine-authorship tell. |
| "Not a stripped-down demo. A real product that solved a real problem." | "a standalone product that solves a real problem" | Strunk 11, positive form. Lead with what it IS. |
| "obsessed over customer feedback" | "answered every feature request, bug report, and churn email personally" | AI slop, LinkedIn modifiers. Also Strunk 12, specific concrete language. |
| "That's it. No growth hacks. No viral loops. No secret sauce." | "We executed three fundamentals consistently. That was the whole strategy." | Williams 7, concision. One strong close replaces four weak fragments. |

## Install

```
claude install-plugin github:poemswe/clarity-and-grace
```

## Skill

The plugin has one skill, `clarity-and-grace:writing`. It activates automatically when Claude writes or edits prose.

## Limitations

The plugin fights tendencies baked into the model's weights. LLMs favor high-probability tokens (Holtzman et al., 2020), distribute information uniformly across sentences (Meister et al.), and approximate language through pattern-matching. The plugin bans specific words, enforces structural rules, and shifts output with before/after examples. Rhythm, surprise, and emphasis still come from the human who edits the final draft.

## Sources

- Thomas & Turner, *Clear and Simple as the Truth* (2011)
- Pinker, *The Sense of Style* (2014)
- Strunk & White, *The Elements of Style* (4th ed.)
- Williams & Bizup, *Style: Lessons in Clarity and Grace* (12th ed.)
- Liang et al., "Monitoring AI-Modified Content at Scale" (2024)
