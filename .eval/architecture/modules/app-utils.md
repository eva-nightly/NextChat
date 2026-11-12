# Module: app/utils [AI]

Provides utility functions and client-side helpers for model list resolution, chat streaming and tool call execution, image processing, state persistence with IndexedDB, cross-device sync (WebDAV/Upstash), authentication signing for cloud providers, and text-to-speech handling.

## Key files
- `app/utils/chat.ts`: Manages multimodal image preprocessing and compression, server-sent events (SSE) chat streaming, animated text rendering, and tool call dispatching.
- `app/utils/model.ts`: Parses, normalizes, sorts, and checks availability for default and custom LLM model identifiers across providers.
- `app/utils/store.ts`: Wraps Zustand store creation with IndexedDB-backed persistence, hydration tracking, and timestamped updates.
- `app/utils/sync.ts`: Extracts, merges, and synchronizes application state (chat sessions, masks, prompts, config, access) between local stores and remote backups.
- `app/utils/stream.ts`: Implements a custom streaming fetch adapter utilizing Tauri IPC events when running in desktop mode or standard window.fetch otherwise.
- `app/utils/cloud/index.ts`: Factory and provider type definitions for cloud sync clients (Upstash Redis and WebDAV).
- `app/utils/tencent.ts`: Generates TC3-HMAC-SHA256 authentication headers for Tencent Hunyuan ChatCompletions API requests.
- `app/utils/ms_edge_tts.ts`: WebSocket-based text-to-speech client for Microsoft Edge speech synthesis.

## Public interface
- createTTSPlayer() (app/utils/audio.ts)
- getAccessToken(clientId, clientSecret) (app/utils/baidu.ts)
- compressImage(file, maxSize), preProcessImageContent(content), uploadImage(file), stream(...) (app/utils/chat.ts)
- deepClone(obj), ensure(obj, keys) (app/utils/clone.ts)
- createSyncClient(provider, config), ProviderType (app/utils/cloud/index.ts)
- createUpstashClient(store) (app/utils/cloud/upstash.ts)
- createWebDavClient(store) (app/utils/cloud/webdav.ts)
- cloudflareAIGatewayUrl(fetchUrl) (app/utils/cloudflare.ts)
- prettyObject(msg), chunks(s, maxBytes) (app/utils/format.ts)
- sign(inputKey, inputData), hash(str), hashWithSecret(str, secret) (app/utils/hmac.ts)
- useAllModels() (app/utils/hooks.ts)
- indexedDBStorage (app/utils/indexedDB-storage.ts)
- merge(target, source) (app/utils/merge.ts)
- getModelProvider(modelWithProvider), collectModelTable(models, customModels), collectModels(models, customModels), collectModelsWithDefaultModel(...), isGPT4Model(modelName), isModelNotavailableInServer(...) (app/utils/model.ts)
- MsEdgeTTS, ProsodyOptions, OUTPUT_FORMAT, PITCH, RATE, VOLUME (app/utils/ms_edge_tts.ts)
- omit(obj, ...keys), pick(obj, ...keys) (app/utils/object.ts)
- createPersistStore(state, methods, persistOptions) (app/utils/store.ts)
- fetch(url, options) (app/utils/stream.ts)
- getLocalAppState(), setLocalAppState(appState), mergeAppState(localState, remoteState) (app/utils/sync.ts)
- getHeader(payload, SECRET_ID, SECRET_KEY) (app/utils/tencent.ts)
- estimateTokenLength(input) (app/utils/token.ts)

## Dependencies
- @next/third-parties/google
- @fortaine/fetch-event-source
- idb-keyval
- zustand
- zustand/middleware
- heic2any

## AI touchpoints [AI]
- `app/utils/cloudflare.ts`
- `app/utils/model.ts`
- `app/utils/sync.ts`
- `app/utils/chat.ts`
- `app/utils/tencent.ts`
- `app/utils/baidu.ts`
- `app/utils/token.ts`

## Open questions
- In app/utils/chat.ts, window._SW_ENABLED determines whether images are uploaded or compressed to base64, but the fallback behavior when service worker registration fails relies on window globals without type declarations.
- In app/utils/ms_edge_tts.ts, the trusted client token is hardcoded in the client source, which could break if Microsoft updates the endpoint token.
