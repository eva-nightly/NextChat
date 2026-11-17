# Module: app/lib

Provides client-side audio processing, realtime microphone recording via AudioWorklet, chunk-based streaming audio playback, frequency visualization analysis, and audio buffer export using the Web Audio API.

## Key files
- `app/lib/audio.ts`: Implements the AudioHandler class for Web Audio context management, PCM audio streaming playback, microphone capture with worklets, and audio blob generation.

## Public interface
- class AudioHandler
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
- _none_

## Open questions
- _none_
