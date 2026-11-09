# Module: test [AI]

Unit and integration test suite for NextChat utility functions, configuration validators, client API helpers, platform detection, cryptographic functions, and MCP action security checks.

## Key files
- `test/mcp-actions-require-enabled.test.ts`: Tests authorization, access control, and gating on MCP Next.js Server Actions.
- `test/model-helpers.test.ts`: Tests model timeouts, reasoning/thinking model classification, and plugin compatibility across service providers.
- `test/collect-model-table.test.ts`: Tests parsing custom model override strings and aggregating model availability tables.
- `test/utils.test.ts`: Tests message content parsing (multimodal text/images, stripped reasoning thoughts), topic trimming, and semantic version comparison.
- `test/vision-model-checker.test.ts`: Tests identification of multimodal vision models by name patterns and VISION_MODELS environment variable configuration.
- `test/hmac-hash.test.ts`: Tests SHA-256 and HMAC-SHA256 cryptographic utility functions.
- `test/adapter.test.ts`: Tests HTTP request adapter URL building, query parameter merging, and response normalization.

## Public interface
- Jest test suite executions covering utility functions, store validation, MCP actions, and client API helpers

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
- `test/utils.test.ts`

## Open questions
- test/model-available.test.ts contains a commented-out failing test marked 'FIXME: 这个测试用例有问题，需要修复' regarding multiple provider fallback resolution.
