# Clarity and Grace

A Claude Code plugin that teaches Claude to write clear, concrete prose.

## What it does

The plugin applies a three-layer writing system whenever Claude writes or edits text that humans will read. Documentation, commit messages, error messages, READMEs, reports, UI copy, explanations. All of it.

The three layers:

1. **Stance** (Thomas & Turner, *Clear and Simple as the Truth*). Write as if pointing something out to an intellectual equal. The motive is truth, not persuasion. The tone is conversational, not ceremonial.

2. **Cognition** (Pinker, *The Sense of Style*). Fight the curse of knowledge. Start from what the reader already knows. Keep working memory load under four items per sentence.

3. **Mechanics** (Strunk, *Elements of Style* + Williams, *Style: Clarity and Grace*). Active voice, positive form, specific language, characters as subjects, actions as verbs, old information before new, emphasis at the end.

The plugin includes condensed reference files for Strunk and Williams with before/after examples for every rule.

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
