# Module: scripts [AI]

Fetches and aggregates predefined chat prompt templates (English, Simplified Chinese, and Traditional Chinese) from remote repositories, filters excluded terms, and writes the structured dataset to public/prompts.json for use as starter masks/prompts.

## Key files
- `scripts/fetch-prompts.mjs`: Node.js script that retrieves prompt collections over HTTP, sanitizes and parses CSV/JSON formats, and generates public/prompts.json.

## Public interface
- node scripts/fetch-prompts.mjs (CLI executable script executing main())

## Dependencies
- node-fetch
- fs/promises

## AI touchpoints [AI]
- `scripts/fetch-prompts.mjs`

## Open questions
- _none_
