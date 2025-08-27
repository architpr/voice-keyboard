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





📌 Assumptions Made

The user runs the project in Google Colab (with microphone access enabled).

A stable internet connection is available for API requests.

The Groq Whisper API endpoint and model (whisper-large-v3) remain accessible.

The audio input is short (e.g., ≤ 30 seconds) and stored as output.wav.

Users have a valid Groq API key and basic familiarity with Python/Colab.



🔑 API Key Configuration Guide

- Get your API key from the Groq Console.

- In your Colab notebook, set the key as an environment variable:

   import os
   os.environ["GROQ_API_KEY"] = "your_api_key_here"


- (Optional, safer) Store the key in Colab Secrets instead of hardcoding:

   - Go to Colab → Tools → Secrets

   - Add a new secret with name GROQ_API_KEY

   - Access it in code:

        import os
        api_key = os.getenv("GROQ_API_KEY")


Verify it’s working by making a simple test call to the transcription API.
