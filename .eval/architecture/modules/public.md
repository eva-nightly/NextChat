# Module: public

Provides client-side worker and processor scripts for the web application, specifically Web Audio recording via an AudioWorklet and client-side file caching/interception via a Service Worker.

## Key files
- `public/audio-processor.js`: Implements AudioRecorderProcessor as an AudioWorkletProcessor to buffer Float32Array PCM audio chunks (2400 samples / 100ms at 24kHz) and post them back to the main thread.
- `public/serviceWorker.js`: Intercepts /api/cache fetch requests to store, retrieve, and delete uploaded client-side files using the browser CacheStorage API.
- `public/serviceWorkerRegister.js`: Registers /serviceWorker.js on DOMContentLoaded, handles update and controller changes, and sets window._SW_ENABLED.

## Public interface
- audio-recorder-processor (AudioWorkletProcessor registered via registerProcessor)
- /api/cache/* (Service Worker intercepted GET, POST, and DELETE endpoints for client file cache)
- window._SW_ENABLED (Boolean flag set when ServiceWorker registration succeeds)

## Dependencies
- Web Audio API (AudioWorkletProcessor, registerProcessor)
- Service Worker API (self.addEventListener, caches, Clients)
- Web Crypto API (crypto.getRandomValues for nanoid generation)

## Open questions
- _none_
