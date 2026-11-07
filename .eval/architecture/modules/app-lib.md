# Module: app/lib

Provides Web Audio API handling for microphone recording, streaming audio playback, frequency analysis visualization, and WAV audio export.

## Key files
- `app/lib/audio.ts`: Defines the AudioHandler class managing AudioContext, AudioWorklet microphone capture, queued PCM chunk streaming playback, frequency analysis, and WAV file construction.

## Public interface
- class AudioHandler
- AudioHandler.prototype.getByteFrequencyData(): Uint8Array
- AudioHandler.prototype.initialize(): Promise<void>
- AudioHandler.prototype.startRecording(onChunk: (chunk: Uint8Array) => void): Promise<void>
- AudioHandler.prototype.stopRecording(): void
- AudioHandler.prototype.startStreamingPlayback(): void
- AudioHandler.prototype.stopStreamingPlayback(): void
- AudioHandler.prototype.playChunk(chunk: Uint8Array): void
- AudioHandler.prototype._saveData(data: Int16Array, bytesPerSample?: number): Blob
- AudioHandler.prototype.savePlayFile(): Blob
- AudioHandler.prototype.saveRecordFile(audioStartMillis: number | undefined, audioEndMillis: number | undefined): Blob
- AudioHandler.prototype.close(): Promise<void>

## Dependencies
- Browser Web Audio API (AudioContext, AudioWorkletNode, ChannelMergerNode, AnalyserNode, AudioBufferSourceNode, MediaStreamAudioSourceNode)
- Browser MediaDevices API (navigator.mediaDevices.getUserMedia)

## Open questions
- The audio worklet module is loaded from public path '/audio-processor.js', which must be present in the public/ static assets.
