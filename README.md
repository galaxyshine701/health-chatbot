# Health & Wellness Assistant

A chatbot that runs fully on your own machine with a small local language model (Ollama, `qwen2.5:0.5b`). It acts as a pre-consultation assistant: it greets the user, asks their name and concern, gathers details such as symptoms, duration and severity, and offers to connect them with a physician. No data leaves the computer and no API key is needed.

Built with Python and Streamlit. There is no live demo, because the model runs locally.

## Features

- Chat interface built with Streamlit, plus a terminal version (`demo.py`)
- Remembers the conversation and addresses the user by name once they share it
- Asks follow-up questions before suggesting a physician
- **Emergency check handled in code, not by the model:** if a message contains a phrase such as "chest pain", "difficulty breathing" or "unconscious", the app skips the model and immediately tells the user to contact emergency services or go to the nearest hospital
- Guardrails set in the system prompt: no medicine dosages, no diagnoses, and polite refusal of non-health topics

## Tech Stack

- Python, Streamlit
- Ollama running `qwen2.5:0.5b`
- OpenAI Python client, pointed at Ollama's local OpenAI-compatible endpoint

## Run Locally

**Requirements:** Python 3.9 or newer and [Ollama](https://ollama.com).

1. Download the model:
   ```bash
   ollama pull qwen2.5:0.5b
   ```
2. Clone the repository and install dependencies:
   ```bash
   git clone https://github.com/galaxyshine701/health-chatbot.git
   cd health-chatbot
   pip install -r requirements.txt
   ```
3. Make sure Ollama is running, then start the app:
   ```bash
   streamlit run app.py
   ```
   To use the terminal version instead, run `python demo.py`.

## Limitations

- This is a general wellness assistant, not a medical device. It does not diagnose and is not a substitute for a doctor.
- The emergency check is a keyword list in English and does not cover every emergency phrase.
- `qwen2.5:0.5b` is a very small model, so answers can be generic or occasionally inaccurate.

## Author

Anam Zubair | [GitHub](https://github.com/galaxyshine701) | [LinkedIn](https://www.linkedin.com/in/anam-zubair-bb1638282)
