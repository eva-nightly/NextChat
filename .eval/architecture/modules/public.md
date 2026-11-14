# Module: public

Provides client-side static worker scripts for browser-level audio worklet stream processing and service worker caching/interception of file assets under /api/cache.

## Key files
- `public/audio-processor.js`: Defines and registers AudioRecorderProcessor as an AudioWorkletProcessor to buffer and stream audio samples over a MessagePort.
- `public/serviceWorker.js`: Intercepts /api/cache requests (GET, POST, DELETE) to store, serve, and manage file uploads using the browser CacheStorage API without backend persistence.
- `public/serviceWorkerRegister.js`: Registers /serviceWorker.js on DOMContentLoaded, manages update lifecycles, and triggers reloads on worker controller changes.

## Public interface
- AudioWorkletProcessor: audio-recorder-processor
- Service Worker fetch interceptor: /api/cache/* (GET, POST, DELETE)
- Global variable: window._SW_ENABLED

## Dependencies
- AudioWorkletProcessor (Web Audio API)
- registerProcessor (Web Audio API)
- caches / CacheStorage (Service Worker API)
- navigator.serviceWorker (Service Worker API)
- crypto.getRandomValues (Web Crypto API)

## Open questions
- _none_
