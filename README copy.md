# LiveKit Voice AI Agent

A simple **Voice AI Agent** built using **LiveKit Agents SDK**, demonstrating the Speech-to-Text (STT) → Large Language Model (LLM) → Text-to-Speech (TTS) pipeline for real-time voice interactions. This project leverages **LiveKit Inference**, a unified, low-latency model gateway that provides access to multiple model providers with just a single LiveKit API key.

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

With one LiveKit API key, you can experiment with all these providers without creating or managing separate accounts.

---

## ⚙️ Technologies Used

* **Python 3.9+**
* **LiveKit Agents SDK**
* **LiveKit Plugins (Noise Cancellation, Silero, Turn Detector)**
* **AssemblyAI (STT)**
* **OpenAI (LLM)**
* **Cartesia (TTS)**
* **dotenv for environment variables**

---

## 📋 Prerequisites

Before you begin, ensure you have:

1. **Python 3.9+** installed on your system
2. **A LiveKit Cloud Account** – Sign up for free at [LiveKit Cloud](https://cloud.livekit.io)

   * LiveKit Cloud includes agent deployment, model inference, and real-time media transport.
   * Create a free project and use the generated **API Key** and **Secret** in the setup.
3. **Git** installed for cloning the repository
4. A terminal or command prompt

---

## 🚀 Getting Started

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/livekit-voice-ai-agent.git
cd livekit-voice-ai-agent
```

### Step 2: Create and Activate Virtual Environment

```bash
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Configure Environment Variables

Create a `.env.local` file in the project root and add your LiveKit credentials:

```bash
LIVEKIT_API_KEY=<your_api_key>
LIVEKIT_API_SECRET=<your_api_secret>
LIVEKIT_URL=<your_livekit_server_url>
```

> ⚠️ **Note:** Never commit `.env.local` to Git. It’s already included in `.gitignore` for security.

### Step 5: Run the Agent

You have multiple ways to run your agent:

* **Development mode (recommended):**

```bash
python agent.py dev
```

This starts the worker in development mode and allows you to connect through the [LiveKit Hosted Playground](https://agents-playground.livekit.io/).

* **Console mode:**

```bash
python agent.py console
```

Start a conversation directly in the console.

* **Other available commands:**

```
connect         Connect to a specific room
download-files  Download plugin dependency files
start           Start the worker in production mode
```

Once running, your Voice AI Agent will connect to the LiveKit server, ready to handle voice conversations in real time.

---

## 🧩 Project Structure

```
.
├── agent.py              # Main AI Agent script
├── requirements.txt      # Python dependencies
├── .env.example          # Example environment file
└── README.md             # Documentation
```

---

## 🧠 How It Works

1. **Speech Input:** Captured from the user and transcribed using AssemblyAI.
2. **Language Processing:** OpenAI LLM processes the text and generates an appropriate response.
3. **Voice Output:** The response is converted to natural audio using Cartesia’s TTS.
4. **Noise Cancellation & VAD:** Handled by LiveKit plugins for improved accuracy and clarity.

---

## 🌐 About LiveKit Inference

**LiveKit Inference** is a low-latency model gateway for voice AI that simplifies integration with top-tier STT, LLM, and TTS providers. It removes the need to manage multiple API accounts and offers:

* Unified API for all model types
* Seamless model switching
* Real-time speech processing
* Free monthly usage credits on every LiveKit Cloud plan

---

## 🧾 License

This project is open-source and available under the **MIT License**.

---

## 💬 Contributing

Feel free to fork this repository and submit pull requests. Contributions and suggestions are always welcome!
