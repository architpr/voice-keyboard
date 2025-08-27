# voice-keyboard

🎤 Voice Keyboard (Groq Whisper API Integration)

This project is a simulation of a custom voice-enabled keyboard.
It mimics the workflow of an iOS custom keyboard extension (UIInputViewController + AVAudioRecorder + Whisper) but implemented in Google Colab (Windows-friendly) using browser-based microphone recording.

Set up an environment where you can record audio (sounddevice) → save/load it (soundfile) → send it to a server/API (requests).

<img width="1919" height="496" alt="Screenshot 2025-08-27 234509" src="https://github.com/user-attachments/assets/efa92437-29d5-41ae-8711-2d0d32c8a821" />

This part just checks file saved or not.

<img width="1916" height="1079" alt="Screenshot 2025-08-27 234544" src="https://github.com/user-attachments/assets/68a0a306-f6ef-462b-9030-d50324a2b2b4" />

It records audio through the browser, sends it to Groq’s Whisper API for transcription, and automatically inserts the recognized text into a text box, simulating how a voice-enabled keyboard would work.

<img width="1916" height="919" alt="Screenshot 2025-08-27 234705" src="https://github.com/user-attachments/assets/e5feb2bc-3c57-4025-83c7-a345029d487d" />

This is the final part where audio file gets converted to text.
<img width="1919" height="924" alt="Screenshot 2025-08-27 234721" src="https://github.com/user-attachments/assets/079e9af7-1574-44f8-9394-4bea3d3fa893" />



🚀 Features

- Press-to-record audio directly in Colab (via browser microphone)

- Save recording as output.wav

- Transcribe audio to text using Groq Whisper API

- Real-time status updates (Idle → Recording → Processing → Done)

- Error handling (missing audio, missing API key, failed API request)

- Export transcription as a .txt file for download

- Supports multiple languages (via Whisper language parameter)



📋 Setup Instructions.
 
- Open the notebook in Google Colab:

- Upload IOS_PROJECT.ipynb

- Run the cells step by step

- Install required Python libraries (only needed if you run outside Colab):

[pip install requests ipywidgets]


📝 Colab already includes most dependencies, but on a local machine (Windows/Linux/Mac) you must install them manually since they are not preinstalled with Python.



⚠️ Known Limitations

- 🎤 Microphone recording works in Google Colab (browser-based capture) but does not work directly in Jupyter Notebook on local PCs. For local use, a library like sounddevice or pyaudio is required.

- 📱 The project simulates iOS keyboard functionality but does not implement UIInputViewController or direct text insertion into apps (not possible in Colab).

- 🌐 Requires an active internet connection since transcription is handled by Groq’s cloud API.

- ⏱️ Recording length is limited to 5 seconds by default for simplicity (can be extended).
