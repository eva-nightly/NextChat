# Module: app/utils [AI]

Provides core utilities for chat streaming, tool-calling orchestration, multimodal image handling, model catalog parsing and filtering, state synchronization (WebDAV/Upstash), persistent IndexedDB store creation, text-to-speech playback, and provider-specific authentication headers.

## Key files
- `app/utils/chat.ts`: Handles chat streaming orchestration, response text animation, tool/function execution loops, and multimodal image caching/compression.
- `app/utils/model.ts`: Parses custom model strings, sorts and manages model availability across providers, and identifies specific model families (such as GPT-4).
- `app/utils/store.ts`: Creates persistent Zustand stores backed by IndexedDB with hydration tracking and custom state updaters.
- `app/utils/indexedDB-storage.ts`: Implements Zustand StateStorage using idb-keyval with fallback to localStorage.
- `app/utils/sync.ts`: Manages extraction, setting, and bidirectional merging of application stores (chat sessions, masks, prompts, config, access) for sync.
- `app/utils/cloud/index.ts`: Provides a factory for creating cloud synchronization clients (WebDAV and Upstash).
- `app/utils/cloud/upstash.ts`: Implements Upstash Redis cloud backup storage with payload chunking.
- `app/utils/cloud/webdav.ts`: Implements WebDAV cloud backup storage.
- `app/utils/stream.ts`: Provides cross-platform fetch utility that hooks into Tauri IPC streaming events when running in desktop mode.
- `app/utils/ms_edge_tts.ts`: Implements a WebSocket client for Microsoft Edge text-to-speech synthesis.
- `app/utils/audio.ts`: Manages Web Audio API AudioContext for TTS playback control.
- `app/utils/tencent.ts`: Computes TC3-HMAC-SHA256 signature headers for Tencent Hunyuan ChatCompletions API requests.
- `app/utils/baidu.ts`: Fetches OAuth access tokens for Baidu services using client ID and secret.
- `app/utils/cloudflare.ts`: Rewrites Cloudflare AI Gateway URLs for Azure, OpenAI, and Anthropic providers.
- `app/utils/token.ts`: Heuristically calculates token length approximations for ASCII and Unicode text.
- `app/utils/hmac.ts`: Pure JavaScript implementation of SHA-256 and HMAC signing for environments lacking SubtleCrypto.
- `app/utils/format.ts`: Formats objects as markdown JSON code blocks and splits strings into byte-safe chunks.
- `app/utils/clone.ts`: Provides deep cloning and object property presence validation.
- `app/utils/merge.ts`: Recursively merges deep object properties with prototype safety checks.
- `app/utils/object.ts`: Provides pick and omit utilities for objects.
- `app/utils/hooks.ts`: React hook providing memoized model lists merged from app config and access store.
- `app/utils/auth-settings-events.ts`: Sends Google Analytics conversion events for authorization and settings page interactions.

## Public interface
- createTTSPlayer()
- trackConversationGuideToCPaymentClick()
- trackAuthorizationPageButtonToCPaymentClick()
- trackAuthorizationPageBannerToCPaymentClick()
- trackSettingsPageGuideToCPaymentClick()
- getAccessToken(clientId, clientSecret)
- compressImage(file, maxSize)
- preProcessImageContentBase(content, transformImageUrl)
- preProcessImageContent(content)
- preProcessImageContentForAlibabaDashScope(content)
- cacheImageToBase64Image(imageUrl)
- base64Image2Blob(base64Data, contentType)
- uploadImage(file)
- removeImage(imageUrl)
- stream(chatPath, requestPayload, headers, tools, funcs, controller, parseSSE, processToolMessage, options)
- deepClone(obj)
- ensure(obj, keys)
- createSyncClient(provider, config)
- createUpstashClient(store)
- createWebDavClient(store)
- cloudflareAIGatewayUrl(fetchUrl)
- prettyObject(msg)
- chunks(s, maxBytes)
- sign(inputKey, inputData)
- hex(bin)
- hash(str)
- hashWithSecret(str, secret)
- useAllModels()
- indexedDBStorage
- merge(target, source)
- getModelProvider(modelWithProvider)
- collectModelTable(models, customModels)
- collectModelTableWithDefaultModel(models, customModels, defaultModel)
- collectModels(models, customModels)
- collectModelsWithDefaultModel(models, customModels, defaultModel)
- isModelAvailableInServer(customModels, modelName, providerName)
- isGPT4Model(modelName)
- isModelNotavailableInServer(customModels, modelName, providerNames)
- MsEdgeTTS
- omit(obj, ...keys)
- pick(obj, ...keys)
- createPersistStore(state, methods, persistOptions)
- fetch(url, options)
- getLocalAppState()
- setLocalAppState(appState)
- mergeAppState(localState, remoteState)
- mergeWithUpdate(localState, remoteState)
- getNonFunctionFileds(obj)
- getHeader(payload, SECRET_ID, SECRET_KEY)
- estimateTokenLength(input)

## Dependencies
- @next/third-parties/google
- @fortaine/fetch-event-source
- idb-keyval
- zustand
- zustand/middleware
- react
- buffer
- crypto
- stream

## AI touchpoints [AI]
- `app/utils/cloudflare.ts`
- `app/utils/model.ts`
- `app/utils/sync.ts`
- `app/utils/chat.ts`
- `app/utils/tencent.ts`
- `app/utils/token.ts`
- `app/utils/ms_edge_tts.ts`

## Open questions
- app/utils/chat.ts uses a dynamic require('heic2any') which may cause runtime errors in non-browser or SSR contexts if not guarded.
- app/utils/chat.ts and app/utils/ms_edge_tts.ts file contents were truncated in the source view.
