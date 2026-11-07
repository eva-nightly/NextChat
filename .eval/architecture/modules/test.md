# Module: test [AI]

Provides Jest/unit test suites verifying application utilities, configuration validators, model metadata filtering, cryptographic helpers, client API adapters, and MCP (Model Context Protocol) server action safeguards.

## Key files
- `test/adapter.test.ts`: Tests the fetch adapter utility for URL concatenation, query params, and response normalisation.
- `test/chat-command-prefix.test.ts`: Tests regular expression matching for chat command prefixes (ASCII and full-width colons).
- `test/cloudflare.test.ts`: Tests URL rewriting and normalization for Cloudflare AI Gateway endpoints.
- `test/collect-model-table.test.ts`: Tests model aggregation, enabling/disabling flags, and custom display names in model tables.
- `test/collect-model-with-default.test.ts`: Tests default model selection and resolution logic in model lists and tables.
- `test/create-message.test.ts`: Tests chat message creation defaults, overrides, and unique ID assignment.
- `test/estimate-token-length.test.ts`: Tests character-based heuristic token length estimation across Latin, ASCII, and CJK characters.
- `test/extract-mcp-json.test.ts`: Tests extraction and parsing of MCP JSON code fences from message content.
- `test/format-chunks.test.ts`: Tests string chunking by byte boundaries without breaking multi-byte characters or words.
- `test/format.test.ts`: Tests JSON formatting and markdown code fence wrapping utility.
- `test/get-bearer-token.test.ts`: Tests Bearer token string formatting and sanitisation for API requests.
- `test/get-client-config.test.ts`: Tests reading configuration from HTML meta tags.
- `test/get-operation-id.test.ts`: Tests deriving operation IDs from HTTP method and path specifications.
- `test/hmac-hash.test.ts`: Tests SHA-256 and HMAC-SHA256 hashing functions against standard test vectors.
- `test/hmac-hex.test.ts`: Tests binary byte array to hex string encoding.
- `test/hmac-sign.test.ts`: Tests cryptographic signing with HMAC-SHA256 returning raw byte buffers.
- `test/is-gpt4-model.test.ts`: Tests classification of model IDs matching GPT-4 and related model families.
- `test/is-mcp-json.test.ts`: Tests regex identification of MCP JSON markdown fences.
- `test/limit-number.test.ts`: Tests numerical boundary clamping and fallback logic.
- `test/mcp-actions-require-enabled.test.ts`: Tests security enforcement and access control ensuring MCP server actions reject unauthenticated or disabled calls.
- `test/mcp-client-environment.test.ts`: Tests isolation of environment variables so application secrets are not passed to MCP child processes.
- `test/merge.test.ts`: Tests deep object merging behavior.
- `test/modal-config-validator.test.ts`: Tests validation and clamping of LLM inference parameters (temperature, max_tokens, penalties, top_p).
- `test/model-available-in-server.test.ts`: Tests server-side custom model availability checking logic.
- `test/model-available.test.ts`: Tests model unavailability checking against custom model strings and environment settings.
- `test/model-helpers.test.ts`: Tests model timeout durations and plugin support matrix across model providers.
- `test/model-provider.test.ts`: Tests splitting model identifiers into model name and provider components.
- `test/object-utils.test.ts`: Tests object manipulation utilities (omit, pick, deepClone, ensure).
- `test/platform-detection.test.ts`: Tests browser user agent platform detection for iOS, Firefox, and macOS.
- `test/prosody-options.test.ts`: Tests SSML prosody configuration defaults and overrides for TTS.
- `test/safe-local-storage.test.ts`: Tests safe in-memory or fallback storage operations.
- `test/sum-module.test.ts`: Basic sanity test suite.
- `test/tts-config-validator.test.ts`: Tests validation and speed clamping for text-to-speech configurations.
- `test/utils.test.ts`: Tests chat utility functions including topic trimming, semver comparison, multimodal message parsing, and DALL-E image sizing.
- `test/valid-string.test.ts`: Tests non-empty string validation helper.
- `test/vision-model-checker.test.ts`: Tests vision model detection logic and custom VISION_MODELS environment variable overrides.

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
- `test/modal-config-validator.test.ts`
- `test/mcp-actions-require-enabled.test.ts`
- `test/extract-mcp-json.test.ts`

## Open questions
- test/model-available.test.ts contains a commented-out test case marked with 'FIXME: 这个测试用例有问题，需要修复' regarding multiple provider handling that may need resolution.
