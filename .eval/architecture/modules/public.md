# Module: public

Provides client-side static worker scripts for audio capture processing (AudioWorklet) and offline/local file caching simulation (Service Worker) under /api/cache.

## Key files
- `public/audio-processor.js`: AudioWorkletProcessor that collects and buffers Float32 audio input chunks (100ms @ 24kHz) during active recording and sends them via message port.
- `public/serviceWorker.js`: Service worker that intercepts /api/cache HTTP requests (GET, POST, DELETE) to persist and serve files locally in the browser's Cache Storage API.
- `public/serviceWorkerRegister.js`: Client script that registers serviceWorker.js on DOMContentLoaded, manages update/controller change reloads, and sets window._SW_ENABLED.

## Public interface
- AudioWorkletProcessor: audio-recorder-processor
- Service Worker intercept routes: GET /api/cache/*, POST /api/cache, DELETE /api/cache/*
- window._SW_ENABLED

## Dependencies
- Web Audio API (AudioWorkletProcessor, registerProcessor)
- Service Worker API (navigator.serviceWorker, caches, ServiceWorkerGlobalScope)
- Web Crypto API (crypto.getRandomValues)

## AI touchpoints [AI]
- `public/audio-processor.js`

## Open questions
- _none_
