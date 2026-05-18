---
name: content-adaptation
description: This skill should be used when the user asks to "adapt Ukrainian copy", "review Ukrainian text", "rewrite Ukrainian website copy", "localize content to Ukrainian", "compare Ukrainian to English source", "check Ukrainian translation", "review UA content", or "improve Ukrainian wording". Use when both an English original and a Ukrainian version are already in context or in the repo, and the task is to revise the Ukrainian so it reads like native Ukrainian rather than a word-for-word translation.
---

# UA Content Adaptation

Rewrite or review an existing Ukrainian version of website text against its English source. Preserve meaning and business intent; rewrite the Ukrainian so it sounds as if it were originally written in Ukrainian.

## Workflow

1. Read the English source and the Ukrainian version in full before making any changes.
2. Treat the English text as the source of meaning, emphasis, tone, and conversion intent — not as a sentence-by-sentence template.
3. Review the Ukrainian as standalone copy first. Flag wording that sounds translated, stiff, overly literal, or commercially weak.
4. Compare the Ukrainian to the English and check for:
   - omitted meaning
   - added meaning not present in the source
   - calques from English syntax or collocations
   - diluted calls to action or weakened commercial positioning
   - terminology inconsistency across similar sections
5. Rewrite the Ukrainian for native fluency while preserving:
   - the original claim and level of specificity
   - the audience fit
   - the tone of confidence and clarity
6. Keep file structure intact. Do not change YAML keys, frontmatter fields, list structure, CTA URLs, or formatting unless the user explicitly asks.
7. After rewriting, read the Ukrainian once more as a native-language quality pass. Remove anything that still sounds like translation.

## Writing Rules

- Prefer adaptive interpretation over literal translation.
- Use idiomatic Ukrainian syntax and collocations.
- Prefer wording that a Ukrainian-speaking professional audience would actually use.
- Keep established product and platform names in their standard form.
- Keep English industry terms only when they are clearly more natural than forced Ukrainian alternatives.
- Avoid visible calques: English sentence rhythm, unnatural noun stacks, and literal renderings of business idioms.
- Preserve strong commercial nuance. If the English copy is precise, confident, or differentiating, the Ukrainian must be equally precise, confident, and differentiating.
- When a direct translation sounds unnatural, rewrite the whole sentence rather than patching individual words.

## Review Output

When asked to review before editing, prioritize findings over summary.

List:
- wording that sounds machine-translated or non-idiomatic
- places where the Ukrainian loses or distorts the English meaning
- suggested replacement wording for each flagged item

If the Ukrainian is already strong, say so explicitly and keep recommendations minimal.

## Edit Output

When asked to apply changes:
- update only the Ukrainian text
- preserve file structure exactly (YAML keys, Markdown headings, list nesting, frontmatter fields)
- keep punctuation and typography consistent with the surrounding file
- prefer a complete sentence rewrite over micro-edits when that produces more natural Ukrainian

## Scope

Apply this skill to existing Ukrainian documents that already have an English source in context.

Do not apply this skill to:
- net-new Ukrainian content with no English source
- legal or certified translation tasks
- pure terminology extraction without copy revision
