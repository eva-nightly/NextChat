# Module: app/lib

Manages browser-side Web Audio API interactions for recording, streaming playback, frequency analysis, and WAV/audio file encoding.

## Key files
- `app/lib/audio.ts`: Implements the AudioHandler class providing audio recording via AudioWorklet, queued audio chunk playback, frequency analysis, and WAV blob exporting.

## Public interface
- AudioHandler.analyser
- AudioHandler.getByteFrequencyData()
- AudioHandler.initialize()
- AudioHandler.startRecording(onChunk: (chunk: Uint8Array) => void)
- AudioHandler.stopRecording()
- AudioHandler.startStreamingPlayback()
- AudioHandler.stopStreamingPlayback()
- AudioHandler.playChunk(chunk: Uint8Array)
- AudioHandler._saveData(data: Int16Array, bytesPerSample?: number): Blob
- AudioHandler.savePlayFile(): Blob
- AudioHandler.saveRecordFile(audioStartMillis?: number, audioEndMillis?: number): Blob
- AudioHandler.close(): Promise<void>

## Dependencies
- _none_

## Open questions
- Where is the /audio-processor.js audio worklet module defined and served from?
