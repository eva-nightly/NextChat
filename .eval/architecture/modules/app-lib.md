# Module: app/lib

Provides low-level Web Audio API management for recording microphone input into PCM chunks, streaming PCM audio playback, visualizing frequency data, and exporting audio buffers to WAV blobs.

## Key files
- `app/lib/audio.ts`: Implements AudioHandler for audio recording via AudioWorklet, queued audio playback, audio spectrum analysis, and WAV file serialization.

## Public interface
- AudioHandler
- AudioHandler.analyser: AnalyserNode
- AudioHandler.prototype.getByteFrequencyData(): Uint8Array
- AudioHandler.prototype.initialize(): Promise<void>
- AudioHandler.prototype.startRecording(onChunk: (chunk: Uint8Array) => void): Promise<void>
- AudioHandler.prototype.stopRecording(): void
- AudioHandler.prototype.startStreamingPlayback(): void
- AudioHandler.prototype.stopStreamingPlayback(): void
- AudioHandler.prototype.playChunk(chunk: Uint8Array): void
- AudioHandler.prototype._saveData(data: Int16Array, bytesPerSample?: number): Blob
- AudioHandler.prototype.savePlayFile(): Blob
- AudioHandler.prototype.saveRecordFile(audioStartMillis?: number, audioEndMillis?: number): Blob
- AudioHandler.prototype.close(): Promise<void>

## Dependencies
- Web Audio API (AudioContext, AudioWorkletNode, AnalyserNode, ChannelMergerNode, MediaStreamAudioSourceNode)
- MediaDevices API (navigator.mediaDevices.getUserMedia)

## Open questions
- _none_
