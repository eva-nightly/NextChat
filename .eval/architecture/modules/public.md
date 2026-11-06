# Module: public

Provides client-side background workers and public scripts: an AudioWorkletProcessor for recording and chunking audio streams in real time, and a Service Worker with its registration script to intercept and manage a local file cache under /api/cache.

## Key files
- `public/audio-processor.js`: Defines and registers AudioRecorderProcessor (AudioWorkletProcessor) that buffers incoming audio chunks (2400 samples) and emits them via MessagePort when recording.
- `public/serviceWorker.js`: Implements service worker fetch interception for /api/cache routes, handling GET, POST (upload), and DELETE using the Cache API.
- `public/serviceWorkerRegister.js`: Registers the service worker on DOMContentLoaded, sets window._SW_ENABLED, and handles reload logic on installation and controller changes.

## Public interface
- AudioWorklet processor name: 'audio-recorder-processor' (handles 'START_RECORDING' and 'STOP_RECORDING' port messages, posts { eventType: 'audio', audioData: Float32Array })
- Service Worker cache endpoints under `/api/cache` (GET matches cache, POST uploads FormData file returning generated URL, DELETE removes cached file)
- Global variable window._SW_ENABLED set by serviceWorkerRegister.js

## Dependencies
- Web Audio API (AudioWorkletProcessor, registerProcessor)
- Service Worker API (navigator.serviceWorker, CacheStorage API, fetch event)
- Web Crypto API (crypto.getRandomValues for nanoid generation)

## AI touchpoints [AI]
- `public/audio-processor.js`

## Open questions
- _none_
