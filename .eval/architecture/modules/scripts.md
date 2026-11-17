# Module: scripts [AI]

Provides build and maintenance utility scripts to download, filter, and compile community system prompts (masks) in Simplified Chinese, Traditional Chinese, and English into a local static JSON file.

## Key files
- `scripts/fetch-prompts.mjs`: Fetches remote prompt datasets from external GitHub mirrors, filters sensitive keywords, formats the prompt pairs, and writes the output to public/prompts.json

## Public interface
- node scripts/fetch-prompts.mjs

## Dependencies
- node-fetch
- fs/promises

## AI touchpoints [AI]
- `scripts/fetch-prompts.mjs`

## Open questions
- _none_
