# 🤖 LiveKit Voice AI Agent

A simple Voice AI Agent built using **LiveKit Agents SDK**, demonstrating the Speech-to-Text (STT) → Large Language Model (LLM) → Text-to-Speech (TTS) pipeline for real-time voice interactions. This project leverages **LiveKit Inference**, a unified, low-latency model gateway that provides access to multiple model providers with just a single LiveKit API key.

This project sets up a voice AI assistant that:

* Joins a LiveKit room.
* Uses STT (Speech-to-Text) for transcription.
* Processes responses using an LLM (Large Language Model).
* Uses TTS (Text-to-Speech) for voice replies.
* Detects voice activity and turns using silero VAD.
* Utilizes LiveKit Inference, a unified, low-latency model gateway that provides access to multiple model providers   with just a single LiveKit API key.

---

## 🧠 Overview

This project demonstrates how to create a fully functional **voice-based AI assistant** using the LiveKit Agents SDK. It connects the following components:

* **STT (Speech-to-Text)** – Converts speech into text.
* **LLM (Large Language Model)** – Processes and generates contextual responses.
* **TTS (Text-to-Speech)** – Converts the response text back into natural-sounding audio.

It uses the **STT → LLM → TTS pipeline**, and we can also use real-time models like **OpenAI** or **Gemini** for creating **speech-to-speech voice agents** instead of relying on the STT → LLM → TTS pipeline.

LiveKit Inference provides a unified API to access models from multiple providers such as:

* **STT:** AssemblyAI, Cartesia, Deepgram
* **LLM:** OpenAI, Google DeepMind, Cerebras, Groq, Baseten
* **TTS:** Cartesia, ElevenLabs, Inworld, Rime

With one LiveKit API key, we can experiment with all these providers without creating or managing separate accounts.

---

## 🧩 Repository Structure

* `agent.py` — Main file that defines and starts the agent.
* `requirements.txt` — Python dependencies.
* `.env.example` — Example environment file(copy to .env.local).
* `README.md` — Documentation (this file).

---

## 📋 Prerequisites

Before running this project, ensure you have:

1. **Python 3.9+** installed on your system
2. **A LiveKit Cloud Account** – Sign up for free at [LiveKit Cloud](https://livekit.io/cloud)

   * LiveKit Cloud includes agent deployment, model inference, and real-time media transport.
   * Create a free project and use the generated **API Key** and **Secret** in the setup.
3. **Git** installed for cloning the repository.

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone <repo-url>
cd voice-ai-agent
```

### 2. Create and activate a virtual environment

#### Windows (PowerShell)

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Copy the example file:

```bash
cp .env.example .env.local
```

Edit `.env.local` and add your LiveKit credentials:

```
LIVEKIT_API_KEY=<your API Key>
LIVEKIT_API_SECRET=<your API Secret>
LIVEKIT_URL=<your LiveKit server URL>
```

### 5. Run the agent

You have multiple ways to run your agent:

* **Development mode:**

```bash
python agent.py dev
```

This starts the worker in development mode and allows you to connect through the [LiveKit Hosted Playground](https://agents-playground.livekit.io/).

* **Console mode:**

```bash
python agent.py console
```

Start a conversation directly in the console.

Once running, your Voice AI Agent will connect to the LiveKit server, ready to handle voice conversations in real time.

---

## ⚠️ Troubleshooting

**1. Agent not connecting:**
Check `LIVEKIT_URL`, `LIVEKIT_API_KEY`, and `LIVEKIT_API_SECRET` in `.env.local`.

**2. Missing packages:**
Ensure your virtual environment is active and dependencies are installed.

**3. Audio not working:**
Confirm the connected client has microphone permissions and joins the same room as the agent.

---