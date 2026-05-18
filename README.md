# ai-plugins

Marketplace repository for AI agent plugins.

## Marketplaces

- Codex marketplace: `.agents/plugins/marketplace.json`
- Claude Code marketplace: `.claude-plugin/marketplace.json`

The marketplace name is `dimanngo/ai-plugins`.

Claude Code can add this repository with:

```sh
claude plugin marketplace add dimanngo/ai-plugins
```

## Plugins

### slide-deck

Deckset-focused presentation plugin with the `deckset` skill. It generates concise Markdown slide decks from articles, notes, briefs, or topics.

The skill behavior:

- Markdown-only output by default.
- Ask for aspect ratio when unspecified, with `16:9` as the recommended default.
- Use minimalist Apple-style presentation design: one idea per slide, very few words, and visuals over dense text.
