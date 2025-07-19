# Personal AI Assistant (Vision + Speech) - Dora


Welcome to **Dora**, a state-of-the-art Personal AI Assistant designed to redefine human-AI interaction. Inspired by the capabilities of Gemini Live, Dora combines real-time vision and speech processing to deliver a seamless, multimodal conversational experience. With Dora, you can speak or type your queries, share visual context via webcam, and receive intelligent, human-like responses powered by cutting-edge AI technologies.

Dora is built with a modular and extensible architecture, leveraging APIs from Groq Cloud, Eleven Labs, and Google, alongside powerful open-source libraries. Whether you're exploring creative ideas, seeking answers, or analyzing visual input, Dora is your witty and reliable companion.

---

## 🌟 Features

- **Multimodal Interaction**: Engage with Dora through audio, text, or webcam for a natural, context-aware experience.
- **Real-Time Speech Processing**: Advanced speech-to-text (`speechrecognition`, Groq Whisper) and text-to-speech (Eleven Labs, gTTS) for fluid conversations.
- **Vision Capabilities**: Analyze webcam input using OpenCV and Groq's vision API to answer context-specific queries (e.g., "Do I have a beard?").
- **Intelligent Agent**: Powered by `langchain` and `langgraph`, Dora dynamically decides when to use vision or text-based responses, guided by a witty system prompt.
- **Interactive UI**: A sleek Gradio interface with live webcam feed and chatbot for intuitive user interaction.
- **Cross-Platform Audio Playback**: Supports audio playback on macOS, Windows, and Linux using platform-specific commands.
- **Secure Configuration**: Uses `python-dotenv` to securely manage API keys.

---

## 🚀 Why Dora?

Dora aligns with the latest trends in AI, positioning it as a forward-thinking project in the rapidly evolving landscape of 2025:

- **Multimodal AI**: The integration of vision, speech, and text is a cornerstone of modern AI applications, seen in products like xAI's Grok and Google's Gemini. Dora's ability to process webcam input and audio in real-time mirrors these advancements.
- **Conversational AI**: With advancements in large language models (LLMs) and speech synthesis, conversational agents are becoming more human-like. Dora leverages Groq's high-performance inference and Eleven Labs' lifelike voices to deliver engaging interactions.
- **Real-Time Processing**: Low-latency processing is critical for interactive applications. Dora's optimized webcam feed (30 FPS, 640x480 resolution) and efficient API calls ensure a responsive experience.
- **Vision-Based AI**: Computer vision is transforming industries like healthcare, education, and retail. Dora's vision capabilities, powered by OpenCV and Groq's vision API, enable context-aware responses.
- **Open-Source Innovation**: The AI community thrives on collaboration. Dora's use of open-source tools like `langchain`, `gradio`, and `opencv-python` ensures accessibility and extensibility.

---

## 🛠️ Technologies Used

Dora is built with a robust stack of modern tools and frameworks:

- **Groq Cloud API**: Powers fast, accurate language and vision processing (Whisper for speech-to-text, LLaMA-based models for vision and text).
- **Eleven Labs API**: Delivers high-quality, multilingual text-to-speech for natural audio responses.
- **Google Gemini API**: Enhances Dora's language understanding via `langchain-google-genai`.
- **Gradio**: Provides a user-friendly web interface with live webcam and chatbot components.
- **LangChain & LangGraph**: Enables dynamic workflows and tool integration for intelligent query handling.
- **OpenCV**: Handles real-time webcam capture and image processing.
- **PyAudio & SpeechRecognition**: Facilitates audio input and speech-to-text conversion.
- **Pydub**: Manages audio processing for high-quality output.
- **Python 3.13 & uv**: Ensures a modern, efficient development environment with fast dependency resolution.

---

## 📋 Requirements

To run Dora, ensure you have the following:

- **Python 3.13**
- **uv** for virtual environment and dependency management

### Required Python Packages

| Package                     | Version       |
|-----------------------------|---------------|
| `elevenlabs`                | >=2.4.0       |
| `gradio`                    | >=5.34.2      |
| `groq`                      | >=0.28.0      |
| `gtts`                      | >=2.5.4       |
| `langchain-google-genai`    | >=2.1.5       |
| `langgraph`                 | >=0.4.8       |
| `opencv-python`             | >=4.11.0.86   |
| `pyaudio`                   | >=0.2.14      |
| `pydub`                    | >=0.25.1      |
| `python-dotenv`             | >=1.1.0       |
| `speechrecognition`         | >=3.14.3      |

---

## ⚙️ Installation

Follow these steps to set up Dora locally:

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/HamzaImtiaz03/Personal-AI-Assistant-Vision-Speech-.git
   cd Personal-AI-Assistant-Vision-Speech-
   ```

2. **Set Up a Virtual Environment with uv**:

   ```bash
   uv venv
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate
   ```

3. **Install Dependencies**:

   ```bash
   uv pip install -r requirements.txt
   ```

4. **Configure API Keys**: Create a `.env` file in the project root with the following:

   ```plaintext
   GROQ_API_KEY=your_groq_api_key
   ELEVENLABS_API_KEY=your_elevenlabs_api_key
   GOOGLE_API_KEY=your_google_api_key
   ```

5. **Run the Application**:

   ```bash
   python main.py
   ```

6. **Access Dora**: Open the Gradio URL (e.g., `http://127.0.0.1:7860`) in your browser to interact with Dora.

---

## 🎮 Usage

Dora is designed for intuitive interaction:

1. **Launch the App**: Run `main.py` to start the Gradio interface.
2. **Start the Webcam**: Click "Start Camera" to enable the live feed (optimized at 640x480, 30 FPS).
3. **Speak or Type**: Use your microphone for continuous listening mode or type queries in the chatbot interface.
4. **Visual Queries**: Ask questions like "Do I have a beard?" to leverage Dora's vision capabilities.
5. **Listen to Responses**: Dora responds with lifelike audio via Eleven Labs or gTTS, played automatically on your system.
6. **End the Session**: Say "goodbye" to exit continuous listening mode.

---

## 🧠 Code Architecture

Dora's codebase is modular and well-organized, ensuring maintainability and scalability:

- **`main.py`**: Orchestrates the Gradio UI, webcam feed, and continuous audio processing loop. It integrates speech-to-text, AI agent responses, and text-to-speech.
- **`tools.py`**: Handles webcam image capture and vision analysis using Groq's vision API, with Base64-encoded image processing for efficient data transfer.
- **`speech_to_text.py`**: Manages audio recording (`PyAudio`, `speechrecognition`) and transcription using Groq's Whisper model.
- **`text_to_speech.py`**: Converts text to audio using Eleven Labs (multilingual, high-quality) and gTTS, with cross-platform playback support.
- **`ai_agent.py`**: Implements the core AI logic using `langchain` and `langgraph`, dynamically routing queries to vision or text processing based on context.

The system prompt in `ai_agent.py` ensures Dora's responses are witty, human-like, and contextually appropriate, with seamless integration of vision tools when needed.

---

## 🌍 Market Relevance

Dora taps into key AI trends driving innovation in 2025:

- **Multimodal AI Assistants**: Companies like xAI (Grok), Google (Gemini), and OpenAI are pushing multimodal AI. Dora's vision and speech capabilities align with this trend, offering a competitive prototype.
- **Real-Time Interaction**: Low-latency processing is critical for applications like virtual assistants and customer support. Dora's optimized webcam feed and API calls ensure responsiveness.
- **Voice-Driven Interfaces**: Voice assistants like Alexa and Grok are increasingly popular. Dora's integration with Eleven Labs delivers lifelike speech synthesis, enhancing user engagement.
- **Vision-Based AI**: Computer vision is revolutionizing industries. Dora's ability to analyze webcam input makes it relevant for applications like education, retail, and accessibility.
- **Open-Source Ecosystems**: Dora's reliance on `langchain`, `gradio`, and `opencv-python` ensures it benefits from community-driven innovation and collaboration.

---

## 🤝 Contributing

Contributions are welcome to enhance Dora's capabilities! To contribute:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -m "Add your feature"`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a Pull Request.

Please adhere to the project's coding standards and include tests where applicable.

---

## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 🙌 Acknowledgments

- **Groq Cloud** for high-performance language and vision processing.
- **Eleven Labs** for lifelike text-to-speech synthesis.
- **Google Gemini API** for advanced language understanding.
- **Open-Source Community** for robust libraries like `langchain`, `gradio`, and `opencv-python`.

---

## 📬 Contact

For questions or feedback, contact the project maintainer:

- **GitHub**: [HamzaImtiaz03](https://github.com/HamzaImtiaz03)
- **Email**: hamza.imtiaz@example.com

Discover Dora and experience the future of AI assistants today!