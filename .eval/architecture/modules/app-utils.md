# Module: app/utils [AI]

Provides utility functions and client-side infrastructure across NextChat, including chat streaming and tool calling orchestration, cloud/WebDAV/Upstash synchronization, Zustand IndexedDB persistence, model list parsing, TTS synthesis, authentication signatures for providers (Tencent, Baidu), and media helpers.

## Key files
- `app/utils/chat.ts`: Orchestrates chat streaming animations, tool execution loops, multimodal image preprocessing, and image uploads.
- `app/utils/store.ts`: Wraps Zustand store creation with persistence and hydration tracking using IndexedDB.
- `app/utils/sync.ts`: Handles synchronization, conflict resolution, and state merging across chat sessions, masks, prompts, and settings.
- `app/utils/model.ts`: Parses custom model specifications, formats provider mappings, and verifies model availability.
- `app/utils/cloud/index.ts`: Factory and types for remote backup sync clients (WebDAV and Upstash Redis).
- `app/utils/stream.ts`: Adapts HTTP fetch for desktop Tauri environments with event-driven streaming and fallback to browser fetch.
- `app/utils/indexedDB-storage.ts`: Implements Zustand StateStorage using idb-keyval with fallback to local storage.
- `app/utils/tencent.ts`: Constructs TC3-HMAC-SHA256 authentication headers for Tencent Hunyuan ChatCompletions API.
- `app/utils/ms_edge_tts.ts`: Microsoft Edge Text-to-Speech WebSocket client for voice synthesis.

## Public interface
- createPersistStore(state, methods, persistOptions)
- stream(chatPath, requestPayload, headers, tools, funcs, controller, parseSSE, processToolMessage, options)
- preProcessImageContent(content)
- preProcessImageContentForAlibabaDashScope(content)
- compressImage(file, maxSize)
- uploadImage(file)
- createSyncClient(provider, config)
- mergeAppState(localState, remoteState)
- getLocalAppState()
- setLocalAppState(appState)
- collectModels(models, customModels)
- collectModelsWithDefaultModel(models, customModels, defaultModel)
- isModelNotavailableInServer(customModels, modelName, providerNames)
- isGPT4Model(modelName)
- useAllModels()
- estimateTokenLength(input)
- fetch(url, options)
- cloudflareAIGatewayUrl(fetchUrl)
- getHeader(payload, SECRET_ID, SECRET_KEY)
- getAccessToken(clientId, clientSecret)
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
- `app/utils/baidu.ts`
- `app/utils/token.ts`
- `app/utils/ms_edge_tts.ts`

## Open questions
- In app/utils/sync.ts, mergeWithUpdate checks both local and remote timestamps using localState.lastUpdateTime; does remoteUpdateTime intended to evaluate remoteState.lastUpdateTime?
- In app/utils/chat.ts, is there a complete fallback mechanism if heic2any fails to load dynamically in non-browser/desktop environments?
