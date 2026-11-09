# Module: app/utils [AI]

Provides core utility functions and helper modules for NextChat, including chat stream orchestration, tool call execution, multimodal image preprocessing, model parsing and availability checking, cross-provider request signing and gateway URL rewriting, local IndexedDB/localStorage storage adapters, cloud sync clients (WebDAV and Upstash), and audio/TTS playback.

## Key files
- `app/utils/chat.ts`: Orchestrates chat streaming responses with frame animation, tool/function call execution, and multimodal image processing and compression.
- `app/utils/model.ts`: Parses, sorts, filters, and validates LLM models and custom model strings across providers.
- `app/utils/store.ts`: Wraps Zustand store creation with IndexedDB persistence, hydration state tracking, and update timestamps.
- `app/utils/indexedDB-storage.ts`: Implements Zustand StateStorage using idb-keyval with localStorage fallback.
- `app/utils/sync.ts`: Merges local and remote application states for chat sessions, prompts, masks, and configuration.
- `app/utils/stream.ts`: Provides a unified streaming fetch implementation switching between browser fetch and Tauri stream events.
- `app/utils/cloud/index.ts`: Factory and interface definitions for WebDAV and Upstash sync clients.
- `app/utils/tencent.ts`: Calculates TC3-HMAC-SHA256 authorization headers for Tencent Hunyuan chat completions.
- `app/utils/cloudflare.ts`: Rewrites API URLs when routing requests through Cloudflare AI Gateway for Azure OpenAI, OpenAI, and Anthropic.
- `app/utils/ms_edge_tts.ts`: WebSocket-based Microsoft Edge text-to-speech synthesis client.
- `app/utils/audio.ts`: Web Audio API player for decoding and playing audio buffers.
- `app/utils/hmac.ts`: Pure JavaScript SHA-256 and HMAC implementation for cryptographic signatures without SubtleCrypto dependencies.
- `app/utils/token.ts`: Heuristic token length estimator for input text.

## Public interface
- createTTSPlayer()
- trackConversationGuideToCPaymentClick(), trackAuthorizationPageButtonToCPaymentClick(), trackAuthorizationPageBannerToCPaymentClick(), trackSettingsPageGuideToCPaymentClick()
- getAccessToken(clientId, clientSecret)
- compressImage(file, maxSize), preProcessImageContent(content), preProcessImageContentForAlibabaDashScope(content), cacheImageToBase64Image(imageUrl), base64Image2Blob(base64Data, contentType), uploadImage(file), removeImage(imageUrl), stream(...)
- deepClone(obj), ensure(obj, keys)
- createSyncClient(provider, config), SyncClients, ProviderType
- createUpstashClient(store)
- createWebDavClient(store)
- cloudflareAIGatewayUrl(fetchUrl)
- prettyObject(msg), chunks(s, maxBytes)
- sign(inputKey, inputData), hex(bin), hash(str), hashWithSecret(str, secret)
- useAllModels()
- indexedDBStorage
- merge(target, source)
- getModelProvider(modelWithProvider), collectModelTable(models, customModels), collectModelTableWithDefaultModel(models, customModels, defaultModel), collectModels(models, customModels), collectModelsWithDefaultModel(models, customModels, defaultModel), isModelAvailableInServer(customModels, modelName, providerName), isGPT4Model(modelName), isModelNotavailableInServer(customModels, modelName, providerNames)
- MsEdgeTTS, ProsodyOptions, OUTPUT_FORMAT, PITCH, RATE, VOLUME
- omit(obj, ...keys), pick(obj, ...keys)
- createPersistStore(state, methods, persistOptions)
- fetch(url, options)
- getLocalAppState(), setLocalAppState(appState), mergeAppState(localState, remoteState), mergeWithUpdate(localState, remoteState)
- getHeader(payload, SECRET_ID, SECRET_KEY)
- estimateTokenLength(input)

## Dependencies
- @fortaine/fetch-event-source
- @next/third-parties/google
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
- app/utils/stream.ts relies on window.__TAURI__ and global events; if Tauri event listeners fail to close on network errors, could memory leaks or dangling TransformStream writers occur?
- app/utils/ms_edge_tts.ts uses hardcoded trusted client tokens and endpoints against Bing speech services which may change or break without notice.
