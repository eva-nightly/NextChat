# Module: scripts [AI]

A build-time or maintenance script that fetches community ChatGPT prompt templates in Simplified Chinese (CN), Traditional Chinese (TW), and English (EN) from remote repositories, filters unwanted keywords, and writes them locally to ./public/prompts.json.

## Key files
- `scripts/fetch-prompts.mjs`: Node.js executable script that pulls, filters, and formats prompt lists from remote sources into a static public JSON file

## Public interface
- node scripts/fetch-prompts.mjs (CLI script execution producing ./public/prompts.json)

## Dependencies
- node-fetch
- fs/promises

## AI touchpoints [AI]
- `scripts/fetch-prompts.mjs`

## Open questions
- The mirror URL domain 'http://raw.fgit.ml/' is hardcoded using HTTP rather than HTTPS; if the mirror goes down or changes, remote prompt fetching will fall back to empty lists.
