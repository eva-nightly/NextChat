# Module: scripts [AI]

A utility script that fetches, filters, and bundles community ChatGPT prompt templates (masks) in Simplified Chinese, Traditional Chinese, and English into a local static asset (./public/prompts.json).

## Key files
- `scripts/fetch-prompts.mjs`: Fetches remote prompt datasets from awesome-chatgpt-prompts repositories via mirror URLs, filters out sensitive keywords, and writes the structured result to ./public/prompts.json.

## Public interface
- node scripts/fetch-prompts.mjs

## Dependencies
- fs/promises
- node-fetch

## AI touchpoints [AI]
- `scripts/fetch-prompts.mjs`

## Open questions
- _none_
