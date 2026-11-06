# 🧠 NEXORA AI – Intelligent Local LLM Chatbot with LangChain Memory

<p align="center">
  <b>Think. Remember. Respond.</b>
</p>

<p align="center">
  An intelligent conversational chatbot powered by a locally running Large Language Model (LLM), LangChain, and Streamlit.
</p>

---

## 📌 Project Overview

**NEXORA AI** is a smart conversational chatbot developed using Python and Streamlit. It uses a locally hosted Large Language Model (LLM) through Ollama to generate intelligent and context-aware responses.

The main objective of this project is to build a personal AI assistant that can understand user questions, maintain conversation history, and remember previous interactions using **LangChain conversational memory**.

Unlike cloud-based AI chatbots, NEXORA AI runs its language model locally, eliminating the need for paid API keys or external AI API services.

It provides a simple, interactive, and user-friendly interface where users can communicate with the AI assistant naturally.

## 🎯 Project Objectives

- To develop an intelligent chatbot using a Local Large Language Model.
- To integrate LangChain for conversational memory management.
- To maintain context from previous user interactions.
- To provide a user-friendly chatbot interface using Streamlit.
- To execute AI model inference locally using Ollama.
- To reduce dependency on paid cloud-based AI services.

<img width="1365" height="632" alt="image" src="https://github.com/user-attachments/assets/3f7966bd-b778-481f-a2aa-fc36674eac20" />


## ✨ Key Features

### 1. Intelligent AI Conversation
- Answers general questions and user queries.
- Generates context-aware responses.
- Provides explanations and useful information.

### 2. Local LLM Integration
- Uses Ollama to execute the language model locally.
- Supports Gemma 3 1B and other configured Ollama models.
- Does not require an external AI API key.

### 3. LangChain Conversational Memory
- Maintains previous conversation messages.
- Provides previous conversation context to the LLM.
- Uses `RunnableWithMessageHistory` for memory management.
- Supports session-based conversation history.

### 4. Interactive Streamlit Interface
- Clean and modern chatbot interface.
- Separate user and AI message displays.
- Chat input for real-time interaction.
- Attractive dark-themed user interface.

### 5. Chat History Management
- Displays messages exchanged during the current session.
- Tracks the number of messages stored in memory.
- Allows users to clear the current conversation.

### 6. Model Selection
- Selects an available local Ollama model.
- Supports multiple configured model options.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Streamlit | Web application interface |
| Ollama | Local LLM execution |
| Gemma 3 1B | Language model |
| LangChain | LLM integration and memory management |
| LangChain Core | Prompt templates and message history |
| langchain-ollama | Ollama model integration |
| UUID | Unique conversation session identification |

## 🧠 System Architecture

```text
              USER
                |
                v
       STREAMLIT CHAT INTERFACE
                |
                v
          USER QUESTION
                |
                v
       LANGCHAIN PROMPT TEMPLATE
                |
                v
      CONVERSATION MEMORY
     (Previous Chat Messages)
                |
                v
           OLLAMA
                |
                v
          GEMMA 3 1B
                |
                v
       AI RESPONSE GENERATION
                |
                v
        STREAMLIT CHAT UI
                |
                v
          USER RESPONSE
```

## 🔄 Working Process

1. The user opens the NEXORA AI chatbot through the Streamlit interface.
2. The user enters a question in the chat input.
3. The chatbot retrieves the previous conversation history using LangChain.
4. The current question and previous messages are passed to the prompt template.
5. Ollama sends the prompt to the locally installed language model.
6. The language model generates an appropriate response.
7. The response is displayed in the Streamlit interface.
8. LangChain updates the conversation history with the new interaction.
9. The chatbot uses this history for subsequent questions.

## 🧩 LangChain Memory Implementation

NEXORA AI uses LangChain's `RunnableWithMessageHistory` to manage conversational memory.

**Important components:**

- `InMemoryChatMessageHistory`: Stores conversation messages temporarily in memory.
- `MessagesPlaceholder`: Inserts previous conversation messages into the prompt.
- `RunnableWithMessageHistory`: Retrieves and updates conversation history for each session.
- `session_id`: Identifies the current conversation session.

**Example Conversation:**

```text
User: My name is Afreen.

NEXORA AI: Nice to meet you!

User: What is my name?

NEXORA AI: Your name is Afreen.
```

This demonstrates how the chatbot uses previous conversation context to answer follow-up questions.

**Note:** The current implementation uses temporary in-memory storage. Conversation history is not permanently saved and may be lost when the application restarts or the session is reset.

## 📂 Project Structure

```text
NEXORA-AI/
│
├── app.py
│
├── requirements.txt
│
├── README.md
│
└── venv/
```

| File | Description |
|---|---|
| `app.py` | Main Streamlit chatbot application |
| `requirements.txt` | Required Python libraries |
| `README.md` | Project documentation |
| `venv/` | Python virtual environment |

## ⚙️ Installation and Setup

### Prerequisites

Before running the project, make sure you have:

- Python 3.11 installed.
- Visual Studio Code.
- Ollama installed.
- Git (optional, for GitHub upload).
- Internet connection for initial package and model downloads.

### Step 1: Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

Navigate into the project folder:

```bash
cd NEXORA-AI
```

Alternatively, download the repository and open the folder directly in VS Code.

### Step 2: Install Ollama

Download Ollama from its official website:

https://ollama.com/download

Install and open Ollama.

### Step 3: Download the Language Model

Open the VS Code terminal and execute:

```bash
ollama pull gemma3:1b
```

This downloads the Gemma 3 1B model to your local computer.

To check installed models:

```bash
ollama list
```

### Step 4: Create a Virtual Environment

For Python 3.11:

```bash
py -3.11 -m venv venv
```

### Step 5: Install Required Dependencies

On Windows PowerShell:

```powershell
.\venv\Scripts\python.exe -m pip install --upgrade pip
```

Install the project dependencies:

```powershell
.\venv\Scripts\python.exe -m pip install -r requirements.txt
```

### Step 6: Run the Application

Execute:

```powershell
.\venv\Scripts\python.exe -m streamlit run app.py
```

The application will open in your default browser.

**Local Application URL:**

http://localhost:8501

## 📦 Requirements

The project dependencies are listed in `requirements.txt`.

```text
streamlit>=1.40.0
langchain>=1.0.0
langchain-core>=1.0.0
langchain-ollama>=0.3.0
```

## 💻 Usage

1. Start the Ollama application.
2. Make sure the selected language model is downloaded.
3. Run the Streamlit application.
4. Open the chatbot in your browser.
5. Enter a question in the message input.
6. Receive an AI-generated response.
7. Continue the conversation and test the chatbot's memory.
8. Use the sidebar to change the model or clear the conversation.

## 🧪 Example Test Cases

| Test Case | Input | Expected Result |
|---|---|---|
| Basic conversation | Hello | AI responds with a greeting |
| General knowledge | What is AI? | Provides an AI explanation |
| Memory testing | My name is Afreen | Stores the message in conversation history |
| Context retrieval | What is my name? | Retrieves the name from previous messages |
| Follow-up question | Explain it with an example | Uses previous conversation context |
| New conversation | Clear Conversation | Starts a fresh session |

## 🔐 Advantages

- No paid AI API subscription is required.
- Runs the language model locally.
- Maintains conversational context.
- Provides a simple and interactive interface.
- Supports multiple local Ollama models.
- Helps understand practical LLM and LangChain integration.

## ⚠️ Limitations

- Requires sufficient system resources to run a local language model.
- Response speed depends on the computer's hardware.
- Conversation memory is temporary.
- The chatbot's knowledge and response quality depend on the selected LLM.
- Internet access is needed for initial installation and model downloads.
- Direct Streamlit Cloud deployment requires a separately accessible model backend; the local Ollama installation is not automatically available in the cloud.

## 🚀 Future Enhancements

The following features can be added in future versions:

- Persistent conversation memory using SQLite or a database.
- Multiple chat sessions and conversation history.
- File upload and document-based question answering.
- Voice input and voice responses.
- AI-powered summarization.
- Custom system prompts and chatbot personalities.
- Improved response streaming.
- Deployment with a remotely accessible LLM backend.

## 🎓 Learning Outcomes

Through this project, the following concepts can be understood:

- Working with Large Language Models.
- Running local AI models using Ollama.
- Integrating LangChain with local LLMs.
- Implementing conversational memory.
- Designing interactive applications using Streamlit.
- Managing Python dependencies and virtual environments.
- Building a complete AI-powered chatbot application.

## 👩‍💻 Author

**AFREEN NISHA M**

Project: NEXORA AI – Intelligent Local LLM Chatbot with LangChain Memory.

## 📄 License

This project is developed for educational and learning purposes.

---

<p align="center">
  <b>NEXORA AI</b><br>
  Think. Remember. Respond. 🧠✨
</p>
