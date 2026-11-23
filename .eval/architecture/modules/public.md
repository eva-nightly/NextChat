# Module: public

Provides client-side background workers and processors, including an AudioWorkletProcessor for buffering audio stream recordings and a Service Worker for intercepting and persisting local file cache requests via the Cache Storage API.

## Key files
- `public/audio-processor.js`: Implements and registers AudioRecorderProcessor (audio-recorder-processor) to accumulate audio input into 100ms (2400 sample) Float32Array buffers and post them through the worklet message port.
- `public/serviceWorker.js`: Service worker script intercepting /api/cache requests to provide client-side GET, POST (file caching with generated nano IDs), and DELETE capabilities using the Cache API.
- `public/serviceWorkerRegister.js`: Initializes and registers the service worker upon DOMContentLoaded, handling reload triggers on updates/controller changes and defining window._SW_ENABLED.

## Public interface
- registerProcessor('audio-recorder-processor', AudioRecorderProcessor)
- AudioWorklet port message command 'START_RECORDING'
- AudioWorklet port message command 'STOP_RECORDING'
- AudioWorklet port message eventType 'audio' with Float32Array audioData
- Service Worker intercepted endpoint: GET /api/cache/*
- Service Worker intercepted endpoint: POST /api/cache/*
- Service Worker intercepted endpoint: DELETE /api/cache/*
- window._SW_ENABLED

## Dependencies
- AudioWorkletProcessor (Web Audio API)
- Service Worker API
- Cache Storage API (caches)
- Web Crypto API (crypto.getRandomValues)

## Open questions
- _none_
