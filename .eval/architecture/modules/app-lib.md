# Module: app/lib

Provides client-side Web Audio API utilities for capturing microphone input, streaming audio chunk playback, visualizer frequency analysis, and generating WAV audio file blobs.

## Key files
- `app/lib/audio.ts`: Implements the AudioHandler class managing microphone recording via AudioWorklet, PCM Int16 chunk streaming, frequency analysis, playback queue, and WAV export.

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

## Dependencies
- Browser Web Audio API (AudioContext, AnalyserNode, AudioWorkletNode, ChannelMergerNode)
- MediaDevices API (navigator.mediaDevices.getUserMedia)
- /audio-processor.js

## Open questions
- In AudioHandler._saveData, the WAV header binary format is constructed but the returned Blob specifies MIME type 'audio/mpeg' rather than 'audio/wav'.
