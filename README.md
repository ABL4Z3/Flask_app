# Audio/Text Emotion Analysis and Empathy Response App

## Overview
This Flask-based web application allows users to upload audio or text files for emotion analysis and empathetic response generation. The app leverages speech-to-text transcription, sentiment analysis, translation, and advanced language models (LangChain Groq) to provide insightful emotional context and empathetic replies based on the input content.

## Features
- Upload audio files (WAV, WEBM) for speech-to-text transcription.
- Upload text files (TXT) for direct emotion analysis.
- Detect emotions (Positive, Negative, Neutral) from transcribed or text content using sentiment analysis.
- Generate empathetic responses using the LangChain Groq language model.
- Support for multiple languages in speech recognition.
- Secure file handling and upload management.
- Detailed logging for monitoring and debugging.

## Installation

1. Clone the repository or download the source code.

2. Create and activate a Python virtual environment (recommended):

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install the required dependencies:

```bash
pip install -r requirements.txt
```

4. Set the environment variable for the Groq API key (optional but recommended):

```bash
export GROQ_API_KEY="your_groq_api_key_here"
```

On Windows (Command Prompt):

```cmd
set GROQ_API_KEY=your_groq_api_key_here
```

## Usage

1. Run the Flask application:

```bash
python app.py
```

2. The server will start on port 8000 by default.

3. API Endpoints:

- `POST /upload-audio`  
  Upload an audio file (`.wav` or `.webm`) with form-data key `audio`. Optionally, specify the language code (default: `en-IN`) in the form-data key `language`.  
  Response includes transcription, detected emotion, and empathetic response.

- `POST /upload_text`  
  Upload a text file (`.txt`) with form-data key `text`.  
  Response includes the text content, detected emotion, and empathetic response.

- `GET /`  
  Returns a welcome message or serves an `index.html` if present.

## Configuration

- `UPLOAD_FOLDER`: Directory where uploaded files are temporarily stored (`uploads` by default).
- `MAX_CONTENT_LENGTH`: Maximum upload size (16MB by default).
- `GROQ_API_KEY`: API key for LangChain Groq model (set as environment variable).

## Dependencies

- Flask
- SpeechRecognition
- TextBlob
- Deep Translator
- LangChain (including langchain-core, langchain-community, langchain-groq)
- PyAudio
- Pydub

## Logging

The application uses Python's built-in logging module to log important events, errors, and debugging information.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Contact

For questions or support, please contact the project maintainer.
