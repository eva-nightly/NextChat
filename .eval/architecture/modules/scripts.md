# Module: scripts [AI]

Fetches and formats community prompt templates in Simplified Chinese, Traditional Chinese, and English from remote repositories and writes them to a static JSON file (public/prompts.json).

## Key files
- `scripts/fetch-prompts.mjs`: Downloads external prompt datasets, filters unwanted entries, and persists the combined prompt dictionary to ./public/prompts.json

## Public interface
- _none_

## Dependencies
- node-fetch
- fs/promises

## AI touchpoints [AI]
- `scripts/fetch-prompts.mjs`

## Open questions
- _none_
