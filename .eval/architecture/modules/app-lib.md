# Module: app/lib

Manages browser-side Web Audio API pipelines for microphone audio recording via AudioWorklet, real-time streaming audio playback queue scheduling, frequency analysis, and WAV file serialization at 24kHz.

## Key files
- `app/lib/audio.ts`: Exports the AudioHandler class managing MediaStream capture, AudioWorklet message handling, streaming chunk playback, frequency analysis, and WAV Blob creation.

## Public interface
- AudioHandler.analyser: AnalyserNode
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

## Dependencies
- Web Audio API (AudioContext, AudioWorkletNode, ChannelMergerNode, AnalyserNode, AudioBufferSourceNode)
- MediaDevices API (navigator.mediaDevices.getUserMedia)
- /audio-processor.js (AudioWorklet module)

## Open questions
- Why does AudioHandler._saveData write a RIFF/WAVE header but export the Blob with MIME type 'audio/mpeg'?
- Is there fallback handling if the browser cannot load /audio-processor.js or does not support AudioWorklet?
