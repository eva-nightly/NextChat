# Module: test [AI]

Unit and regression test suite verifying application utility functions, model resolution/filtering rules, formatting, cryptographic HMAC operations, client configuration parsers, and MCP server action access and security controls.

## Key files
- `test/adapter.test.ts`: Tests the fetch adapter utility for joining base URLs, parameters, and formatting HTTP response objects
- `test/chat-command-prefix.test.ts`: Tests the regular expression for chat command prefixes (ASCII and CJK full-width colons)
- `test/cloudflare.test.ts`: Tests Cloudflare AI Gateway URL rewriting and formatting rules
- `test/collect-model-table.test.ts`: Tests model resolution and custom model additions/overrides into model tables
- `test/collect-model-with-default.test.ts`: Tests default model selection and flagging within model tables
- `test/create-message.test.ts`: Tests the factory function for creating chat message objects with default metadata and IDs
- `test/estimate-token-length.test.ts`: Tests token length estimation heuristic calculations across different character sets
- `test/extract-mcp-json.test.ts`: Tests extraction and JSON parsing of MCP code fences from message text
- `test/format-chunks.test.ts`: Tests UTF-8 safe word and byte chunking generator logic
- `test/format.test.ts`: Tests formatting and JSON markdown code-fence enclosure helpers
- `test/get-bearer-token.test.ts`: Tests API Bearer token header formatting and whitespace normalization
- `test/get-client-config.test.ts`: Tests DOM meta-tag parsing for client-side configuration
- `test/get-operation-id.test.ts`: Tests operationId extraction and HTTP method/path derivation
- `test/hmac-hash.test.ts`: Tests SHA-256 and HMAC-SHA256 hex hashing functions against test vectors
- `test/hmac-hex.test.ts`: Tests byte array to hex string encoding utilities
- `test/hmac-sign.test.ts`: Tests raw byte HMAC-SHA256 signature generation
- `test/is-gpt4-model.test.ts`: Tests model name recognition for GPT-4 family variants
- `test/is-mcp-json.test.ts`: Tests regex identification of MCP-specific json fences in message text
- `test/limit-number.test.ts`: Tests numerical boundary clamping and fallback defaults
- `test/mcp-actions-require-enabled.test.ts`: Tests authentication and enablement checks protecting Next.js Server Actions for MCP management
- `test/mcp-client-environment.test.ts`: Verifies process environment isolation for child MCP processes to prevent secret leaks
- `test/merge.test.ts`: Tests deep object merging and mutation logic
- `test/modal-config-validator.test.ts`: Tests validation and clamping of model hyperparameters (max_tokens, temperature, penalties)
- `test/model-available-in-server.test.ts`: Tests checking server-side model availability and explicit disabling strings
- `test/model-available.test.ts`: Tests model availability filters against custom model configuration strings and environment variables
- `test/model-helpers.test.ts`: Tests request timeout resolution per model type and plugin support capabilities per provider
- `test/model-provider.test.ts`: Tests parsing model strings into separate model names and provider names
- `test/object-utils.test.ts`: Tests object utility functions including pick, omit, deepClone, and ensure
- `test/platform-detection.test.ts`: Tests user-agent detection for iOS, Firefox, and macOS platforms
- `test/prosody-options.test.ts`: Tests Microsoft Edge TTS SSML prosody configuration defaults and instances
- `test/safe-local-storage.test.ts`: Tests storage abstraction wrapping localStorage key/value operations
- `test/sum-module.test.ts`: Basic sanity test for testing framework runner setup
- `test/tts-config-validator.test.ts`: Tests TTS speed, engine, model, and voice validator clamps
- `test/utils.test.ts`: Tests topic trimming, semver comparison, multimodal message parsing (text/images/reasoning extraction), and model sizing utilities
- `test/valid-string.test.ts`: Tests non-empty string validation helper
- `test/vision-model-checker.test.ts`: Tests detection of vision-capable models via regex and VISION_MODELS environment variable overrides

## Public interface
- _none_

## Dependencies
- util
- @jest/globals

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
- `test/create-message.test.ts`
- `test/estimate-token-length.test.ts`
- `test/extract-mcp-json.test.ts`
- `test/get-bearer-token.test.ts`
- `test/is-mcp-json.test.ts`
- `test/mcp-actions-require-enabled.test.ts`
- `test/mcp-client-environment.test.ts`
- `test/modal-config-validator.test.ts`
- `test/model-provider.test.ts`
- `test/utils.test.ts`

## Open questions
- In test/model-available.test.ts, a test case for multiple providers is commented out with a FIXME marker indicating a known bug in provider availability matching.
