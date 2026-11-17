# Module: public

Provides client-side public browser scripts for service worker registration, offline/client-side file caching via service worker interceptors on `/api/cache`, and real-time audio chunk recording using AudioWorklet.

## Key files
- `public/audio-processor.js`: Implements and registers an AudioWorkletProcessor ('audio-recorder-processor') that buffers input audio samples at 24kHz and emits chunked Float32Array buffers over MessagePort.
- `public/serviceWorker.js`: Service worker handling install/activation events and intercepting `/api/cache` requests (GET, POST, DELETE) to store, serve, and remove client-cached files using CacheStorage.
- `public/serviceWorkerRegister.js`: Client script executed on DOMContentLoaded that registers /serviceWorker.js, handles controller updates, and sets `window._SW_ENABLED = true`.

## Public interface
- registerProcessor('audio-recorder-processor', AudioRecorderProcessor) - AudioWorklet processor registered for recording audio buffers
- ServiceWorker fetch interceptor on /api/cache (GET, POST, DELETE) for virtual file cache endpoints
- window._SW_ENABLED boolean flag set upon service worker registration

## Dependencies
- Web Audio API (AudioWorkletProcessor, registerProcessor)
- Service Worker API (ServiceWorkerGlobalScope, CacheStorage, caches)
- Web Crypto API (crypto.getRandomValues)

## AI touchpoints [AI]
- `public/audio-processor.js`

## Open questions
- Are there cleanup routines or expiration policies for files stored in CHATGPT_NEXT_WEB_FILE_CACHE to prevent unbounded storage growth in the browser cache?
