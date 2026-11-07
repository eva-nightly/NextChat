# Module: app/utils [AI]

Provides client-side and server-side utilities for chat streaming, multimodal image processing, LLM model catalog filtering and token estimation, cloud/local state synchronization (Upstash, WebDAV, IndexedDB), signature generators for third-party AI APIs (Tencent Hunyuan, Baidu), TTS playback, and analytics tracking.

## Key files
- `app/utils/chat.ts`: Implements SSE chat streaming orchestration, tool invocation lifecycles, and multimodal image upload/compression/preprocessing.
- `app/utils/model.ts`: Parses custom model strings, sorts and indexes LLM models with provider mappings, and verifies model availability.
- `app/utils/store.ts`: Wraps Zustand state stores with IndexedDB persistence, hydration tracking, and immutable state updates.
- `app/utils/sync.ts`: Handles synchronization and deep merging across local and remote application stores (chat sessions, masks, prompts, configs).
- `app/utils/stream.ts`: Abstracts fetch requests to support both standard browser fetch and Tauri IPC-based native streaming.
- `app/utils/cloud/index.ts`: Factory and types for remote backup sync clients (WebDAV and Upstash Redis).
- `app/utils/tencent.ts`: Constructs TC3-HMAC-SHA256 authenticated headers for Tencent Hunyuan ChatCompletions API requests.
- `app/utils/token.ts`: Estimates prompt and completion token counts across ASCII and Unicode character sets.

## Public interface
- stream(chatPath, requestPayload, headers, tools, funcs, controller, parseSSE, processToolMessage, options)
- compressImage(file, maxSize)
- uploadImage(file)
- preProcessImageContent(content)
- collectModels(models, customModels)
- collectModelsWithDefaultModel(models, customModels, defaultModel)
- isModelNotavailableInServer(customModels, modelName, providerNames)
- estimateTokenLength(input)
- createPersistStore(state, methods, persistOptions)
- indexedDBStorage
- createSyncClient(provider, config)
- mergeAppState(localState, remoteState)
- getHeader(payload, SECRET_ID, SECRET_KEY)
- getAccessToken(clientId, clientSecret)
- cloudflareAIGatewayUrl(fetchUrl)
- createTTSPlayer()
- MsEdgeTTS

## Dependencies
- @fortaine/fetch-event-source
- @next/third-parties/google
- idb-keyval
- zustand
- heic2any

## AI touchpoints [AI]
- `app/utils/cloudflare.ts`
- `app/utils/model.ts`
- `app/utils/sync.ts`
- `app/utils/chat.ts`
- `app/utils/tencent.ts`
- `app/utils/token.ts`

## Open questions
- In app/utils/sync.ts, mergeWithUpdate reads 'const remoteUpdateTime = localState.lastUpdateTime ?? 1;', which appears to be a bug reading localState instead of remoteState.lastUpdateTime.
