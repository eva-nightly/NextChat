# Module: test [AI]

Unit and regression test suite verifying core utilities, chat message formatting, HMAC cryptography, MCP actions and parsing, model table filtering and selection, token length estimation, config validation, and platform detection.

## Key files
- `test/mcp-actions-require-enabled.test.ts`: Tests MCP server actions access control and authorization checks to prevent unauthorized execution
- `test/collect-model-table.test.ts`: Tests parsing, enabling/disabling, and naming of built-in and custom AI models across providers
- `test/model-helpers.test.ts`: Tests model-specific timeouts (reasoning/thinking vs standard chat) and plugin capability flags across providers
- `test/cloudflare.test.ts`: Tests URL rewriting and normalization for Cloudflare AI Gateway endpoints
- `test/estimate-token-length.test.ts`: Tests token length estimation heuristics for Latin, ASCII, and multi-byte CJK text
- `test/modal-config-validator.test.ts`: Tests range clamping and fallback validation for model parameters like temperature, top_p, and max_tokens
- `test/hmac-hash.test.ts`: Tests SHA-256 and HMAC-SHA256 hashing utility logic against standard test vectors
- `test/utils.test.ts`: Tests chat message text extraction, thinking/reasoning tag filtering, image extraction, and semver comparison

## Public interface
- _none_

## Dependencies
- @jest/globals
- util
- ../app/client/api
- ../app/command
- ../app/config/client
- ../app/constant
- ../app/mcp/actions
- ../app/mcp/client
- ../app/mcp/utils
- ../app/store/chat
- ../app/store/config
- ../app/utils
- ../app/utils/clone
- ../app/utils/cloudflare
- ../app/utils/format
- ../app/utils/hmac
- ../app/utils/merge
- ../app/utils/model
- ../app/utils/ms_edge_tts
- ../app/utils/object
- ../app/utils/token

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
- `test/extract-mcp-json.test.ts`
- `test/is-mcp-json.test.ts`
- `test/estimate-token-length.test.ts`
- `test/utils.test.ts`

## Open questions
- In test/model-available.test.ts, a test case for multiple provider availability resolution is commented out with a FIXME noting the test needs fixing.
