# Module: test [AI]

Provides unit and regression test coverage for NextChat client utilities, configuration validators, model metadata filtering, cryptographic helpers, chat message formatters, and Model Context Protocol (MCP) server action authorization.

## Key files
- `test/adapter.test.ts`: Tests custom HTTP fetch adapter query string assembly, URL handling, and response structure normalization.
- `test/collect-model-table.test.ts`: Validates model table collection, parsing custom model identifiers, and provider overrides.
- `test/estimate-token-length.test.ts`: Tests token estimation across ASCII, Latin, and multi-byte CJK character sets.
- `test/mcp-actions-require-enabled.test.ts`: Verifies that Next.js Server Actions for MCP tools require ENABLE_MCP and valid access code authorization.
- `test/mcp-client-environment.test.ts`: Confirms that spawned MCP child processes do not inherit sensitive application environment variables.
- `test/modal-config-validator.test.ts`: Tests clamping and validation for model generation parameters (max_tokens, temperature, top_p, penalties).
- `test/model-helpers.test.ts`: Verifies timeout selection for thinking/reasoning models and plugin support flags across service providers.
- `test/utils.test.ts`: Tests message content parsing (multimodal extraction, reasoning/thinking prefix stripping) and topic string trimming.
- `test/vision-model-checker.test.ts`: Tests vision model detection logic against predefined patterns and custom environment overrides.

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
- `test/estimate-token-length.test.ts`
- `test/mcp-actions-require-enabled.test.ts`
- `test/utils.test.ts`

## Open questions
- In test/model-available.test.ts, a test case for multiple providers where a model is available on one provider is commented out with a FIXME notation indicating it needs fixing.
