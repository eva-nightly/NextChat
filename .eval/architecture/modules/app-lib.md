# Module: app/lib

Provides Web Audio API handling for recording microphone audio input via AudioWorklet, streaming playback of incoming PCM audio chunks, frequency analysis, and exporting recorded or played audio as WAV/audio Blobs.

## Key files
- `app/lib/audio.ts`: Implements the AudioHandler class for real-time audio capture, chunked PCM playback scheduling, frequency visualization analysis, and WAV file encapsulation.

## Public interface
- AudioHandler
- AudioHandler.prototype.getByteFrequencyData
- AudioHandler.prototype.initialize
- AudioHandler.prototype.startRecording
- AudioHandler.prototype.stopRecording
- AudioHandler.prototype.startStreamingPlayback
- AudioHandler.prototype.stopStreamingPlayback
- AudioHandler.prototype.playChunk
- AudioHandler.prototype.savePlayFile
- AudioHandler.prototype.saveRecordFile
- AudioHandler.prototype.close
- AudioHandler.prototype.analyser

## Dependencies
- /audio-processor.js

## Open questions
- AudioHandler._saveData sets the Blob MIME type to 'audio/mpeg' despite encoding a standard RIFF/WAVE header; it is unclear if consumers expect MP3 or WAV format.
