# voice-keyboard

🎤 Voice Keyboard (Groq Whisper API Integration)

This project is a simulation of a custom voice-enabled keyboard.
It mimics the workflow of an iOS custom keyboard extension (UIInputViewController + AVAudioRecorder + Whisper) but implemented in Google Colab (Windows-friendly) using browser-based microphone recording.

🚀 Features

Press-to-record audio directly in Colab (via browser microphone)

Save recording as output.wav

Transcribe audio to text using Groq Whisper API

Real-time status updates (Idle → Recording → Processing → Done)

Error handling (missing audio, missing API key, failed API request)

Export transcription as a .txt file for download

Supports multiple languages (via Whisper language parameter)

📋 Setup Instructions

Clone this repository:

git clone https://github.com/<your-username>/voice-keyboard-colab.git
cd voice-keyboard-colab


Open the notebook in Google Colab:

Upload colab_voice_keyboard.ipynb

Run the cells step by step

Install required Python libraries (only needed if you run outside Colab):

pip install requests ipywidgets


📝 Colab already includes most dependencies, but on a local machine (Windows/Linux/Mac) you must install them manually since they are not preinstalled with Python.

⚠️ Known Limitations

🎤 Microphone recording works in Google Colab (browser-based capture) but does not work directly in Jupyter Notebook on local PCs. For local use, a library like sounddevice or pyaudio is required.

📱 The project simulates iOS keyboard functionality but does not implement UIInputViewController or direct text insertion into apps (not possible in Colab).

🌐 Requires an active internet connection since transcription is handled by Groq’s cloud API.

⏱️ Recording length is limited to 5 seconds by default for simplicity (can be extended).
