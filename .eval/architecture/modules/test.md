# Module: test [AI]

Unit and integration test suite covering utility functions, MCP action security and execution guards, model table generation and validation, formatters, cryptography, and client configuration.

## Key files
- `test/mcp-actions-require-enabled.test.ts`: Tests authorization and environment configuration gates for MCP Next.js server actions.
- `test/mcp-client-environment.test.ts`: Tests environment variable isolation when spawning MCP child processes.
- `test/collect-model-table.test.ts`: Tests model discovery, parsing custom model configuration strings, and status flags.
- `test/cloudflare.test.ts`: Tests URL rewriting logic for Cloudflare AI Gateway endpoints.
- `test/modal-config-validator.test.ts`: Tests validation and boundary clamping for LLM generation parameters.
- `test/utils.test.ts`: Tests text extraction, thinking line filters, multimodal image extraction, semver comparisons, and model size checkers.

## Public interface
- _none_

## Dependencies
- ../app/utils
- ../app/utils/model
- ../app/utils/cloudflare
- ../app/utils/token
- ../app/utils/format
- ../app/utils/hmac
- ../app/utils/merge
- ../app/utils/object
- ../app/utils/clone
- ../app/utils/ms_edge_tts
- ../app/mcp/actions
- ../app/mcp/client
- ../app/mcp/utils
- ../app/store/chat
- ../app/store/config
- ../app/config/client
- ../app/client/api
- ../app/command
- ../app/constant

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
- `test/modal-config-validator.test.ts`
- `test/mcp-actions-require-enabled.test.ts`
- `test/estimate-token-length.test.ts`

## Open questions
- A test in test/model-available.test.ts is commented out with a FIXME stating that handling multiple providers when a model is available on one provider needs fixing.
