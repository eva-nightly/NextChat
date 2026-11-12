# Module: public

Provides static client-side browser runtime scripts for offline file caching via Service Worker interception and audio recording stream processing using an AudioWorkletProcessor.

## Key files
- `public/audio-processor.js`: Implements AudioRecorderProcessor, an AudioWorkletProcessor that buffers input audio chunks and posts formatted Float32Array audio data messages back to the main thread on recording commands.
- `public/serviceWorker.js`: Intercepts client-side /api/cache fetch requests to handle offline/browser-level file uploads, retrievals, and deletions via the Cache API using a custom nanoid generator.
- `public/serviceWorkerRegister.js`: Registers /serviceWorker.js upon DOMContentLoaded, sets window._SW_ENABLED, and handles reload logic on worker installation and controller change.

## Public interface
- AudioRecorderProcessor (registered AudioWorklet as audio-recorder-processor)
- Service Worker fetch listener for /api/cache (GET, POST, DELETE)
- window._SW_ENABLED

## Dependencies
- Web Audio API (AudioWorkletProcessor, registerProcessor)
- Service Worker API (self.addEventListener, caches, clients)
- Web Crypto API (crypto.getRandomValues)

## Open questions
- What component or hook loads audio-processor.js into the AudioWorklet and receives the audio events posted by AudioRecorderProcessor?
- Which parts of the UI trigger POST/GET/DELETE requests to /api/cache for client-side file attachment caching?
