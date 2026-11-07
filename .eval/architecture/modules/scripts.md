# Module: scripts [AI]

A utility build/data-fetching script that retrieves curated ChatGPT prompt templates (masks/presets) in Simplified Chinese, Traditional Chinese, and English from external repositories, filters excluded words, and compiles them into public/prompts.json.

## Key files
- `scripts/fetch-prompts.mjs`: Fetches remote prompt collections, filters terms, and writes the structured output to ./public/prompts.json.

## Public interface
- CLI execution: node scripts/fetch-prompts.mjs (outputs public/prompts.json)

## Dependencies
- node-fetch
- fs/promises

## AI touchpoints [AI]
- `scripts/fetch-prompts.mjs`

## Open questions
- Is raw.fgit.ml still an active and reliable mirror host for GitHub raw files?
- Should fallback to direct GitHub raw endpoints (RAW_FILE_URL) be implemented when the mirror fails?
