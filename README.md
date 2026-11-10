# 🎙️ AI Interview Twin

An AI-powered interview assistant that allows interviewers to interact with a personalized AI version of a candidate through voice or text. The application uses Large Language Models (LLMs) to generate contextual interview responses based on the candidate's profile and background.

Built with **Python, Streamlit, Groq API, Whisper, and GPT-OSS 20B**.

## 🚀 Project Overview

AI Interview Twin is an interactive web application designed to simulate an interview conversation using a candidate's personal and professional profile.

An interviewer can ask questions using a microphone, type questions manually, or select predefined sample questions. The application processes the input and generates personalized responses using an LLM.

The generated answers are displayed in a conversational interface and can optionally be played aloud using browser-based speech synthesis.

**The application uses prompt-based personalization rather than training or fine-tuning a custom AI model.**

## ✨ Key Features

- **Voice-Based Interaction:** Record interview questions using the microphone.
- **Speech-to-Text:** Convert spoken questions into text using Whisper.
- **AI-Powered Responses:** Generate contextual interview answers using GPT-OSS 20B through Groq.
- **Personalized AI Assistant:** Use candidate information stored in `profile.txt` to generate relevant responses.
- **Text-Based Interaction:** Submit interview questions directly through the application.
- **Sample Interview Questions:** Explore predefined questions for quick interaction.
- **Text-to-Speech:** Listen to generated responses using browser speech synthesis.
- **Conversation History:** Maintain conversation context using Streamlit session state.
- **Interactive Interface:** Simple and responsive web interface built with Streamlit.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Streamlit | Web application interface |
| Groq API | Hosted AI inference |
| Whisper | Speech-to-text transcription |
| GPT-OSS 20B | Personalized response generation |
| JavaScript | Browser-based speech playback |
| Streamlit Session State | Conversation management |
| Git & GitHub | Version control |
| Streamlit Community Cloud | Application deployment |

## 🏗️ Application Architecture

The application follows a simple AI-powered processing workflow.

```text
       Interviewer
            |
     Voice / Text Input
            |
     Streamlit Interface
            |
      Input Processing
            |
    +-------+--------+
    |                |
 Voice Input     Text Input
    |                |
  Whisper         Direct Text
    |                |
    +-------+--------+
            |
      User Question
            |
    Candidate Profile
       (profile.txt)
            |
      System Prompt
            |
       Groq API
            |
      GPT-OSS 20B
            |
   Personalized Answer
            |
      Streamlit UI
            |
     Browser Speech
       Synthesis
```

## 📂 Project Structure

```text
100x_streamlit_voicebot/
│
├── app.py
│   └── Main Streamlit application
│
├── profile.txt
│   └── Candidate background and interview context
│
├── requirements.txt
│   └── Python dependencies
│
├── README.md
│   └── Project documentation
│
└── .gitignore
    └── Files excluded from version control (if configured)
```

## ⚙️ Installation and Setup

### 1. Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
```

### 2. Navigate to the Project Directory

```bash
cd 100x_streamlit_voicebot
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

Activate the environment:

**macOS / Linux**

```bash
source venv/bin/activate
```

**Windows**

```bash
venv\Scripts\activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Configure the Groq API Key

Obtain an API key from [Groq Console](https://console.groq.com/).

For local development, create a `.streamlit/secrets.toml` file:

```toml
GROQ_API_KEY = "your_groq_api_key"
```

Alternatively, configure the environment variable:

```bash
export GROQ_API_KEY="your_groq_api_key"
```

**Important:** Never commit API keys or other credentials to a public GitHub repository.

### 6. Run the Application

```bash
streamlit run app.py
```

The application will open in your browser, usually at:

```text
http://localhost:8501
```

## 🔄 How It Works

1. **User Input:** The interviewer records a voice question, types a question, or selects a sample question.
2. **Speech Recognition:** If voice input is selected, Whisper converts the recorded audio into text through the Groq API.
3. **Profile Loading:** The application reads the candidate's background and professional information from `profile.txt`.
4. **Prompt Engineering:** The candidate profile is included in the system prompt to provide personalized context.
5. **LLM Processing:** The question and recent conversation history are sent to GPT-OSS 20B through Groq.
6. **Response Generation:** The model generates a personalized answer based on the available profile information.
7. **Response Display:** The answer is displayed in the Streamlit chat interface.
8. **Voice Playback:** The interviewer can listen to the generated answer using the browser's built-in speech synthesis.

## 🔐 Security and Configuration

- API credentials are managed through Streamlit Secrets or environment variables.
- Sensitive configuration files should be excluded using `.gitignore`.
- The application requires a valid Groq API key to access the AI services.
- Avoid storing private candidate information in a public repository.

## ☁️ Deployment

The application can be deployed using **Streamlit Community Cloud**.

Deployment steps:

1. Push the project files to a GitHub repository.
2. Open [Streamlit Community Cloud](https://share.streamlit.io/).
3. Connect your GitHub account.
4. Select the project repository.
5. Set `app.py` as the application entry point.
6. Add `GROQ_API_KEY` under application Secrets.
7. Deploy the application.

## ⚠️ Current Limitations

- Candidate information is loaded from a static text file.
- Conversation history is maintained using session state and is not permanently stored in a database.
- Browser speech synthesis depends on the available browser and device voices.
- The application does not use a custom-trained or voice-cloned model.
- Prompt-based personalization can still produce inaccurate responses, so generated answers should be reviewed.

## 🔮 Future Improvements

- Integrate a persistent database for conversation storage.
- Introduce candidate profile management.
- Add authentication and user access controls.
- Integrate dedicated text-to-speech services for more consistent voice output.
- Improve response evaluation and factual accuracy.
- Add interview feedback, scoring, and performance analytics.
- Implement automated testing and application monitoring.

## 🎯 Learning Outcomes

Through this project, I gained practical experience in:

- Building interactive AI applications using Python and Streamlit.
- Integrating Large Language Models through hosted APIs.
- Implementing speech-to-text functionality using Whisper.
- Applying prompt engineering for personalized AI responses.
- Managing conversation context using session state.
- Handling API credentials and external service integrations.
- Deploying Python applications using GitHub and Streamlit Community Cloud.

## 👨‍💻 Author

**K. Hari Saketh**

AI/ML & Generative AI Enthusiast

---

⭐ If you find this project interesting, feel free to explore the repository and share your feedback.
