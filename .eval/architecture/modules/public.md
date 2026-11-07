# Module: public

Provides client-side worker scripts for real-time audio input buffering (via AudioWorklet) and local browser file caching/interception (via Service Worker) to support offline storage and media handling.

## Key files
- `public/audio-processor.js`: Defines and registers AudioRecorderProcessor, an AudioWorkletProcessor that buffers audio stream input in chunks (2400 samples/100ms) and posts buffer events to the main thread.
- `public/serviceWorker.js`: Implements service worker fetch interception on '/api/cache' to locally handle file upload (POST), retrieval (GET), and deletion (DELETE) using the browser Cache API.
- `public/serviceWorkerRegister.js`: Registers '/serviceWorker.js' upon DOMContentLoaded and handles lifecycle reload events.

## Public interface
- AudioWorklet processor name: 'audio-recorder-processor'
- AudioWorklet port message commands: START_RECORDING, STOP_RECORDING
- AudioWorklet port message output: { eventType: 'audio', audioData: Float32Array }
- Service Worker intercepted route: /api/cache (GET, POST, DELETE)
- Global variable: window._SW_ENABLED

## Dependencies
- Web Audio API (AudioWorkletProcessor, registerProcessor)
- Service Worker API (CacheStorage, caches, self, navigator.serviceWorker)
- Web Crypto API (crypto.getRandomValues)

## AI touchpoints [AI]
- `public/audio-processor.js`

## Open questions
- _none_
