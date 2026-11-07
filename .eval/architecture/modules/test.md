# Module: test [AI]

Unit and regression test suite verifying application utilities, cryptographic hashing, client configuration, Model Context Protocol (MCP) handlers, model selection and token estimation logic, and storage helpers.

## Key files
- `test/mcp-actions-require-enabled.test.ts`: Verifies access controls and enablement guards for MCP server actions
- `test/collect-model-table.test.ts`: Tests model table construction, custom model configuration parsing, and provider tagging
- `test/collect-model-with-default.test.ts`: Validates model collection resolution and default model flagging
- `test/estimate-token-length.test.ts`: Tests heuristic token length calculation across character classes
- `test/vision-model-checker.test.ts`: Validates vision model identification regex patterns and environment overrides
- `test/model-helpers.test.ts`: Verifies model timeout selection (e.g. reasoning/thinking models) and plugin support per provider
- `test/cloudflare.test.ts`: Tests Cloudflare AI Gateway URL parsing and normalization
- `test/adapter.test.ts`: Tests HTTP fetch adapter parameter joining and response normalization
- `test/create-message.test.ts`: Tests chat message creation defaults and ID generation in the chat store

## Public interface
- _none_

## Dependencies
- ../app/utils
- ../app/utils/model
- ../app/utils/token
- ../app/utils/format
- ../app/utils/hmac
- ../app/utils/merge
- ../app/utils/object
- ../app/utils/clone
- ../app/utils/cloudflare
- ../app/utils/ms_edge_tts
- ../app/client/api
- ../app/command
- ../app/constant
- ../app/config/client
- ../app/store/chat
- ../app/store/config
- ../app/mcp/utils
- ../app/mcp/actions
- ../app/mcp/client
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
- `test/extract-mcp-json.test.ts`
- `test/mcp-actions-require-enabled.test.ts`

## Open questions
- A test case in test/model-available.test.ts is commented out with a FIXME indicating multiple provider fallback behavior needs fixing.
