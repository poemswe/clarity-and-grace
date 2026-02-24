# Clarity and Grace

A Claude Code plugin that teaches Claude to write clear, concrete prose.

## What it does

The plugin applies a three-layer writing system whenever Claude writes or edits text that humans will read. Documentation, commit messages, error messages, READMEs, reports, UI copy, explanations. All of it.

The three layers:

1. **Stance** (Thomas & Turner, *Clear and Simple as the Truth*). Write as if pointing something out to an intellectual equal. The motive is truth, not persuasion. The tone is conversational, not ceremonial.

2. **Cognition** (Pinker, *The Sense of Style*). Fight the curse of knowledge. Start from what the reader already knows. Keep working memory load under four items per sentence.

3. **Mechanics** (Strunk, *Elements of Style* + Williams, *Style: Clarity and Grace*). Active voice, positive form, specific language, characters as subjects, actions as verbs, old information before new, emphasis at the end.

The plugin includes four condensed reference files with before/after examples for every rule, plus an AI slop ban list with rule citations for every category.

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

> We reached $100K ARR without paid ads. Eighteen months of focus on three things got us there.
>
> We built in public and shared every win, failure, and pivot. People followed the journey and became customers because they felt invested.
>
> We made our free tier a standalone product that solves a real problem. Users who got genuine value became our best evangelists.
>
> We answered every feature request, bug report, and churn email personally.
>
> We executed three fundamentals consistently. That was the whole strategy.

**What changed**

| Before | After | Rule |
|---|---|---|
| "It wasn't magic and it wasn't luck" | Cut | Strunk 11, positive form. Say what IS. |
| "Here's how" | Cut | Williams 7, concision. The post already shows how. |
| "It was eighteen months of relentless focus" | "Eighteen months of focus... got us there" | Williams 1, characters as subjects. Remove empty "it was." |
| "Every win, every failure, every pivot was shared openly" | "shared every win, failure, and pivot" | Strunk 10, active voice. |
| "Not a stripped-down demo. A real product that solved a real problem." | "a standalone product that solves a real problem" | Strunk 11, positive form. Lead with what it IS. |
| "That's it. No growth hacks. No viral loops. No secret sauce." | "We executed three fundamentals consistently. That was the whole strategy." | Williams 7, concision. One strong close replaces four weak fragments. |

## Install

```
claude install-plugin github:poemswe/clarity-and-grace
```

## Skill

The plugin provides one skill, `clarity-and-grace:writing`, which activates automatically when Claude writes or edits prose. No manual invocation needed.

## Sources

- Thomas & Turner, *Clear and Simple as the Truth* (2011)
- Pinker, *The Sense of Style* (2014)
- Strunk & White, *The Elements of Style* (4th ed.)
- Williams & Bizup, *Style: Lessons in Clarity and Grace* (12th ed.)
- Liang et al., "Monitoring AI-Modified Content at Scale" (2024)
