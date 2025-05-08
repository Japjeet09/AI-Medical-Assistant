# AI Doctor with Vision and Voice

An interactive AI-powered assistant that simulates a doctor's consultation using computer vision and voice technologies.

## DEMO

*Deployed locally at http://127.0.0.1:7860*

## FEATURES

- **Voice Input**: Record patient's questions or concerns using microphone input.
- **Image Analysis**: Upload medical images for AI diagnosis and assessment.
- **Speech-to-Text**: Converts patient's voice input to text using Whisper model.
- **AI Diagnosis**: Analyzes images with LLaMA 4 Scout vision model for medical assessment.
- **Voice Response**: Converts AI-generated medical advice to natural speech output.
- **Gradio Interface**: User-friendly web interface for seamless interaction.
- **Multi-modal Interaction**: Combines voice, text, and image processing in one application.

## TOOLS USED

- **Groq**: Cloud AI platform for running large language models (LLaMA 4 Scout) and speech-to-text (Whisper).
- **ElevenLabs**: Text-to-speech API for natural-sounding voice output.
- **gTTS (Google Text-to-Speech)**: Alternative TTS option for voice generation.
- **Gradio**: Web interface framework for creating ML applications.
- **PyDub**: Audio processing library for handling audio files.
- **SpeechRecognition**: Library for microphone input and audio processing.
- **Base64**: For encoding and decoding image data.
- **Python-dotenv**: For loading environment variables.

## COMPONENTS

- **brain_of_the_doctor.py**: Handles image analysis using Groq's vision models.
- **voice_of_the_patient.py**: Manages voice recording and speech-to-text functionality.
- **voice_of_the_doctor.py**: Handles text-to-speech conversion for AI responses.
- **gradio_app.py**: Main application that integrates all components with a web interface.

## SETUP INSTRUCTIONS

### Prerequisites
- Python 3.8+
- Required API keys:
  - Groq API key
  - ElevenLabs API key

### Installation

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/ai-doctor.git
   cd ai-doctor
   ```

2. Create a virtual environment and activate it:
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

4. Create a `.env` file with your API keys:
   ```
   GROQ_API_KEY=your_groq_api_key
   ELEVENLABS_API_KEY=your_elevenlabs_api_key
   ```

### Running the Application

Launch the Gradio web interface:
```
python gradio_app.py
```

Access the application in your web browser at: `http://127.0.0.1:7860`

## USAGE

1. **Record Your Question**: Click the microphone button and speak your medical question.
2. **Upload an Image**: Upload a medical image showing the area of concern.
3. **Submit**: Click the submit button to process your inputs.
4. **Review Results**:
   - View the text transcription of your question
   - Read the doctor's assessment of your image
   - Listen to the voice response

## TECHNICAL DETAILS

### System Prompt

The AI doctor uses the following system prompt for image analysis:

```python
system_prompt="""You have to act as a professional doctor, i know you are not but this is for learning purpose. 
What's in this image?. Do you find anything wrong with it medically? 
If you make a differential, suggest some remedies for them. Donot add any numbers or special characters in 
your response. Your response should be in one long paragraph. Also always answer as if you are answering to a real person.
Donot say 'In the image I see' but say 'With what I see, I think you have ....'
Dont respond as an AI model in markdown, your answer should mimic that of an actual doctor not an AI bot, 
Keep your answer concise (max 2 sentences). No preamble, start your answer right away please"""
```

### API Usage Flow

1. Voice input → Whisper transcription via Groq
2. Image + transcribed query → LLaMA 4 Scout analysis via Groq
3. AI response → Voice synthesis via ElevenLabs

## LIMITATIONS

- For educational purposes only - not a substitute for professional medical advice
- Limited to supported languages in speech recognition and synthesis
- Requires internet connection for API access
- AI analysis accuracy depends on image quality and model capabilities

## FUTURE ENHANCEMENTS

- Add support for multiple languages
- Implement conversation history
- Integrate medical knowledge databases
- Add specialized medical image preprocessing
- Develop mobile application version

## DISCLAIMERS

This application is for educational and demonstration purposes only. It is not intended to provide actual medical diagnosis or replace consultation with qualified healthcare professionals. Always seek proper medical advice from licensed physicians for health concerns.

## REFERENCES

- [Groq Documentation](https://console.groq.com/docs)
- [ElevenLabs Documentation](https://docs.elevenlabs.io/)
- [Gradio Documentation](https://www.gradio.app/docs/)
- [LLaMA Models](https://llama.meta.com/)
- [Whisper Models](https://github.com/openai/whisper)
