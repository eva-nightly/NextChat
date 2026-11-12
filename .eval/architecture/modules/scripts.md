# Module: scripts [AI]

Fetches, sanitizes, and aggregates external community ChatGPT prompt lists across multiple locales (Simplified Chinese, Traditional Chinese, and English) into a static JSON artifact at public/prompts.json.

## Key files
- `scripts/fetch-prompts.mjs`: CLI script that downloads remote prompt datasets from external mirrors, filters out banned terms, and writes public/prompts.json

## Public interface
- node scripts/fetch-prompts.mjs

## Dependencies
- node-fetch
- fs/promises

## AI touchpoints [AI]
- `scripts/fetch-prompts.mjs`

## Open questions
- _none_
