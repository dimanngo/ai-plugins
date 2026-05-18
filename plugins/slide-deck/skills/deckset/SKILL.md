---
name: deckset
description: Generate Deckset-compatible Markdown presentations from articles, notes, briefs, or topics. Use when the user asks for a slide deck, presentation, executive briefing, architecture review deck, tech-talk slides, or a Deckset Markdown file.
---

# Deckset

Create a well-structured presentation in Markdown using Deckset conventions. Your primary role is presentation designer and storyteller, not coder.

## What Deckset Is

Deckset is a macOS presentation app that turns a plain Markdown file into designed slides. The agent writes the source Markdown; Deckset handles layout, rendering, presenting, and export.

Deckset is not Reveal.js, Marp, PowerPoint, or HTML. Do not use syntax from those tools unless it is also valid Deckset Markdown.

## Inputs

- User goal, notes, topic, article URL, or source text.
- Audience and tone when specified by the user.
- Optional output destination. If the user asks for a file, create `presentation.md` or the requested filename. Otherwise return only the completed Markdown deck.

## Precedence Rules

- Output format is Markdown-only unless the user explicitly asks you to write a file or include explanation.
- Aspect ratio is not assumed silently when the user has not specified it. Ask the user which ratio they want and suggest:
  - `16:9` recommended/default
  - `1:1`
  - another custom ratio
- Presentation style is minimalist Apple-style storytelling with one idea per slide, very few words, and visuals preferred over dense text.

## Mandatory Preflight

Before drafting slides:

1. Stop and analyze the user's goal, source material, audience, and intended setting.
2. Query Deckset documentation before drafting:
   - Prefer Context7 MCP library `/websites/deckset_english_lproj`.
   - Ask specifically for Deckset Markdown syntax, configuration commands, slide directives, image modifiers, presenter notes, and Mermaid support.
   - If Context7 MCP is unavailable, read Deckset LLM documentation from `https://context7.com/websites/deckset_english_lproj/llms.txt`.
3. Read the local syntax samples in `references/` when available:
   - `deckset-basics.md`
   - `deckset-images.md`
   - `deckset-big-text.md`
   - `deckset-tables.md`
4. Treat official Deckset documentation as source of truth and local samples as syntax/style references.
5. If the source is an article URL and network access is unavailable, ask the user for the article text or a local copy.

## Presentation Style

- Each slide conveys one idea only.
- Prefer single words, short phrases, key numbers, diagrams, charts, or images over paragraphs.
- Use more slides instead of packing too much onto one slide.
- Keep slides suitable for executive briefings, architecture reviews, or tech talks.
- Default audience, unless the user says otherwise: Solution Architects, Enterprise Architects, Developers, and Engineering Managers.
- Default tone: professional, approachable, precise, thorough, and accessible.
- Build a clear story arc: setup, problem, insight, solution, proof, implications, takeaway.
- Keep the deck visually clean: whitespace, high contrast, large readable text.
- Avoid clutter, dense bullet lists, long sentences, and unnecessary detail.
- Put extra detail into appendix slides when needed.

## Deck Structure

Use this structure unless the user's material calls for a better story:

1. Title slide with a clear, impactful title.
2. Agenda or overview slide with the main flow.
3. Content slides broken into small story beats.
4. Summary or key takeaways.
5. Closing slide with a call to action, Q&A prompt, or memorable final point.

## Deckset Syntax Primer

Use this notation unless official Deckset docs say otherwise:

- Start a new slide with `---` on its own line, with blank lines around it.
- Use Markdown headings for visual hierarchy:
  - `#` large title
  - `##` regular heading
  - `###` smaller heading
- Use global configuration commands at the top of the file, for example:
  - `theme: Poster, 1`
  - `autoscale: true`
  - `build-lists: true`
  - `slide-transition: fade(0.3)`
- Use per-slide commands in square brackets, for example:
  - `[.hide-footer]`
  - `[.slidenumbers: false]`
  - `[.build-lists: false]`
- Use `^` paragraphs for presenter notes.
- Use Deckset image modifiers:
  - `![](image.jpg)` background image
  - `![fit](image.jpg)` fit full image
  - `![left](image.jpg)` or `![right](image.jpg)` split slide
  - `![inline 40%](image.jpg)` inline image
- Use plain Mermaid code fences only. Do not add Mermaid YAML/frontmatter config.

## Deckset Formatting

- Write valid Markdown with Deckset features.
- Separate slides with `---`.
- Use headings for slide titles.
- Use Deckset slide directives intentionally, for example `[.hide-footer]` and `[.slidenumbers: false]`.
- Use Deckset configuration at the top when the user requests a complete deck.
- Use `build-lists: true`, `autoscale: true`, `list: alignment(left)`, `slidenumbers: true`, `slidecount: true`, and `slide-transition: fade(0.3)` unless the user asks otherwise.
- Do not use Reveal.js syntax such as `<!-- .element: class="fragment" -->`.
- Do not include Mermaid frontmatter config blocks. Mermaid diagrams must start directly with plain Mermaid syntax such as `graph`, `flowchart`, or `sequenceDiagram`.

## Image And Readability Rules

- Avoid placing dense text on complex images.
- Use Deckset image modifiers deliberately:
  - `![](image)` for background image behavior.
  - `![fit](image)` for full-image visibility.
  - `![left](image)`, `![right](image)`, `![left fit](image)`, or `![right fit](image)` for split layouts with readable text space.
  - `![inline](image)` or `![inline 40%](image)` for image-with-text composition.
- For data-rich visuals, prefer a title-only setup slide followed by an image-only slide using `[.hide-footer]`, `[.slidenumbers: false]`, and `![fit](...)`.
- If text over an image is unavoidable, keep the text extremely short.
- Do not rely on image defaults when readability depends on layout.

## Output Rules

- If returning inline, output only the Markdown presentation.
- If writing a file, create `presentation.md` unless the user requested another path, and keep the assistant response short with the file path and any assumptions.
- Do not include commentary, planning notes, or explanations inside the deck unless they are actual slide content.
- Keep Deckset paths realistic for the user's project. Do not invent local image paths unless clearly marked as placeholders.
