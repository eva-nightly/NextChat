# Module: app/lib

Provides an AudioHandler utility using the Web Audio API for recording microphone input via AudioWorklet, streaming playback of audio chunks, frequency analysis, and exporting recorded/played audio buffers as WAV blobs.

## Key files
- `app/lib/audio.ts`: Implements the AudioHandler class managing Web Audio context, input capture, chunk conversion, streaming audio playback, and file export formatting.

## Public interface
- AudioHandler.constructor()
- AudioHandler.getByteFrequencyData(): Uint8Array
- AudioHandler.initialize(): Promise<void>
- AudioHandler.startRecording(onChunk: (chunk: Uint8Array) => void): Promise<void>
- AudioHandler.stopRecording(): void
- AudioHandler.startStreamingPlayback(): void
- AudioHandler.stopStreamingPlayback(): void
- AudioHandler.playChunk(chunk: Uint8Array): void
- AudioHandler.savePlayFile(): Blob
- AudioHandler.saveRecordFile(audioStartMillis?: number, audioEndMillis?: number): Blob
- AudioHandler.close(): Promise<void>
- AudioHandler.analyser: AnalyserNode

## Dependencies
- _none_

## Open questions
- The AudioWorklet processor module '/audio-processor.js' is loaded from an absolute root path at runtime, which requires a corresponding public asset.
