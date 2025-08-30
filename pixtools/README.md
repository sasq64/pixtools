# Pixtools

A collection of multimedia utilities for AI-powered applications.

## Features

- **TextToSpeech**: Convert text to speech using OpenAI's TTS API
- **VoiceToText**: Convert speech to text using OpenAI's Whisper API  
- **AudioPlayer**: Audio playback capabilities
- **OpenAIClient**: Wrapper for OpenAI API interactions
- **FileCache**: File-based caching system with metadata support
- **ImageGen**: AI image generation using OpenAI's DALL-E

## Installation

```bash
# Install from local directory
pip install -e /path/to/pixtools

# Or install from git repository
pip install git+https://github.com/yourusername/pixtools.git
```

## Usage

```python
from pixtools import TextToSpeech, VoiceToText, AudioPlayer
from pixtools import OpenAIClient, FileCache, ImageGen

# Initialize components
cache = FileCache("./cache")
client = OpenAI(api_key="your-key")
audio_player = AudioPlayer()

# Text-to-speech
tts = TextToSpeech(audio_player, cache, client, voice="alloy")
tts.speak("Hello, world!")

# Voice-to-text
vtt = VoiceToText(client)
vtt.start_transribe()
# ... record audio ...
future = vtt.end_transcribe()
text = future.result()
```

## Requirements

- Python 3.10+
- OpenAI API key
- PyAudio for audio functionality