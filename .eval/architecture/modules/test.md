# Module: test [AI]

Provides unit and regression test coverage for core utilities, client/server configuration, chat stores, MCP actions and parsing, cryptography helpers, token estimation, and model capability/provider parsing.

## Key files
- `test/mcp-actions-require-enabled.test.ts`: Verifies access controls and authentication enforcement for MCP server actions when ENABLE_MCP and CODE environment variables are set or unset.
- `test/collect-model-table.test.ts`: Tests model table generation, provider mapping, custom model syntax parsing, and enablement flags.
- `test/collect-model-with-default.test.ts`: Tests resolving and marking default models from model tables with and without provider qualification.
- `test/model-helpers.test.ts`: Tests model timeout durations for thinking/reasoning models and plugin support per provider.
- `test/vision-model-checker.test.ts`: Tests regex identification and environment-based configuration for multimodal vision models.
- `test/utils.test.ts`: Tests utility functions for chat topic trimming, version comparisons, multimodal image/text parsing, and thinking block stripping.
- `test/estimate-token-length.test.ts`: Tests character-based token estimation heuristics across ASCII, Latin, and CJK text.
- `test/adapter.test.ts`: Tests HTTP adapter request and URL query assembly alongside fetch response normalization.

## Public interface
- _none_

## Dependencies
- @jest/globals
- util

## AI touchpoints [AI]
- `test/cloudflare.test.ts`
- `test/collect-model-table.test.ts`
- `test/collect-model-with-default.test.ts`
- `test/is-gpt4-model.test.ts`
- `test/model-available-in-server.test.ts`
- `test/model-available.test.ts`
- `test/model-helpers.test.ts`
- `test/tts-config-validator.test.ts`
- `test/vision-model-checker.test.ts`
- `test/mcp-actions-require-enabled.test.ts`
- `test/mcp-client-environment.test.ts`
- `test/extract-mcp-json.test.ts`
- `test/is-mcp-json.test.ts`
- `test/estimate-token-length.test.ts`
- `test/utils.test.ts`

## Open questions
- In test/model-available.test.ts, there is a disabled/commented out test case marked 'FIXME' regarding multiple provider availability checks.
