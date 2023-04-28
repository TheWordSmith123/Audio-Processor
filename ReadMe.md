   AudioProcessor Documentation body { font-family: Arial, sans-serif; line-height: 1.6; } h1, h2, h3 { margin-bottom: 0.5rem; } ul { margin-left: 1.5rem; margin-bottom: 1rem; } code { background-color: #f1f1f1; padding: 2px 4px; border-radius: 4px; }

AudioProcessor
==============

`AudioProcessor` is a Python class that provides functionality for recording audio, transcribing audio to text, and converting text to audio.

Class Methods
-------------

### `__init__(self, frame_duration_ms=30, sample_rate=16000, chunk_size=1024, vad_mode=2)`

Initialize the `AudioProcessor` class.

**Parameters:**

*   `frame_duration_ms`: Frame duration in milliseconds (default: 30 ms)
*   `sample_rate`: Audio sample rate (default: 16000 Hz)
*   `chunk_size`: Audio chunk size for processing (default: 1024)
*   `vad_mode`: Voice Activity Detection (VAD) mode (default: 2)

### `record_audio(self, output_file_path)`

Record audio from the microphone and save it to a .wav file.

**Parameters:**

*   `output_file_path`: Output file path for the recorded audio

### `audio_to_text(self, audio_file_path, **kwargs)`

Transcribe an audio file.

**Parameters:**

*   `audio_file_path`: Input audio file path
*   `**kwargs`: Keyword arguments for preprocessing and other options

**Returns:**

*   Transcribed text as a string

### `text_to_audio(self, text, audio_file_path, lang='en', volume=1.0, sample_rate=44100, bit_depth=16)`

Convert text to an audio file and play it.

**Parameters:**

*   `text`: Input text to convert to audio
*   `audio_file_path`: Output audio file path
*   `lang`: Language of the text (default: 'en')
*   `volume`: Volume level of the output audio (default: 1.0)
*   `sample_rate`: Audio sample rate (default: 44100 Hz)
*   `bit_depth`: Audio bit depth (default: 16)

Private Methods
---------------

These methods are used internally by the class and should not be called directly by the user.

### `_save_audio_to_file(self, audio, file_path)`

Save the audio data to a .wav file.

### `_process_audio_text(self, audio_text, **kwargs)`

Process the audio\_text and return the transcribed text.

### `_parse_recognition_response(self, response, show_all)`

Parse the response from the speech recognizer.

### `_process_recognized_audio(self, audio)`

Process the recognized audio and return the transcribed text.

### `_play_audio_file(self, audio_file_path, volume=1.0, normalize=False)`

Play the audio file with the specified volume and optional normalization.

### `_generate_frames(self, audio, sample_rate, frame_duration_ms)`

Generate audio frames from raw audio data.

### `_collect_voiced_segments(self, frames, vad, sample_rate, ratio=2)`

Collect voiced segments from audio frames using the Voice Activity Detection (VAD) algorithm.