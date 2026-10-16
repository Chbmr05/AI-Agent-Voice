# AI-Agent-Voice

# 🤖 AI Voice Sales & Course Booking Agent

An AI-powered voice calling agent designed to automate course enquiries, assist prospective students, answer frequently asked questions, recommend courses, and schedule demo sessions through conversational voice interactions.

Built using **Python, Flask, Twilio, and Google Generative AI**, the system helps educational institutes streamline student communication and automate their initial course counselling and sales workflows.

## 📌 Table of Contents

* [Overview](#-overview)
* [Key Features](#-key-features)
* [Technology Stack](#-technology-stack)
* [System Architecture](#-system-architecture)
* [Supported Courses](#-supported-courses)
* [Project Structure](#-project-structure)
* [How It Works](#-how-it-works)
* [Installation and Setup](#-installation-and-setup)
* [Environment Variables](#-environment-variables)
* [Running the Application](#-running-the-application)
* [Example Conversation](#-example-conversation)
* [Use Cases](#-use-cases)
* [Future Improvements](#-future-improvements)
* [Contributing](#-contributing)
* [License](#-license)

## 📖 Overview

Educational institutes receive numerous enquiries from students interested in technical courses, career opportunities, and training programs. Handling these enquiries manually can require significant time and resources.

The AI Voice Sales & Course Booking Agent addresses this challenge by automating conversations with prospective students.

The application uses Twilio for voice communication, Flask to handle webhooks and application logic, and Google Generative AI for conversational intelligence.

The agent can understand student enquiries, provide relevant course information, manage the conversation flow, collect student preferences, and facilitate demo session bookings.

The application uses conversation state to maintain relevant information throughout an interaction.

## ✨ Key Features

### 1. AI-Powered Voice Interactions

* Supports automated voice conversations through Twilio.
* Processes student responses and enquiries.
* Generates contextually relevant conversational responses.

### 2. Intelligent Course Enquiries

* Answers frequently asked questions about courses.
* Provides information about course fees, schedules, internships, placements, projects, and certifications.
* Helps prospective students understand available training programs.

### 3. Course Selection

* Supports Python Full Stack and Java Full Stack course enquiries.
* Tracks the course a student is interested in.
* Uses the conversation context to guide subsequent interactions.

### 4. Stateful Conversation Management

* Maintains application-level conversation state.
* Tracks the current conversation stage.
* Records relevant details such as course interest, questions, and student preferences.
* Uses workflow logic to guide conversations toward an appropriate next step.

### 5. Demo Session Scheduling

* Collects student preferences for demo sessions.
* Captures relevant booking information, including the student's name, mobile number, preferred date, and time.
* Supports booking confirmation workflows.

### 6. Automated Sales Workflow

* Guides prospective students through course discovery.
* Responds to common questions and objections.
* Identifies student interests and preferences.
* Helps move conversations from initial enquiries toward demo bookings.

### 7. Webhook-Based Integration

* Uses Flask endpoints to receive and process Twilio webhook requests.
* Integrates voice interactions with backend application logic.
* Supports communication between the telephony layer and conversational workflow.

### 8. Booking Data Management

* Stores booking information using the application's configured data-storage mechanism.
* Supports structured tracking of student details and demo preferences.

## 🛠️ Technology Stack

| Technology           | Purpose                                                 |
| -------------------- | ------------------------------------------------------- |
| Python               | Core programming language                               |
| Flask                | Backend application and webhook handling                |
| Twilio               | Voice calling and telephony integration                 |
| Google Generative AI | AI-powered conversational responses                     |
| REST APIs            | Communication between application components            |
| python-dotenv        | Environment variable management                         |
| JSON                 | Structured storage of application data where configured |

## 🏗️ System Architecture

The application follows a modular workflow connecting voice communication, backend processing, conversational intelligence, and booking management.

```text
        Prospective Student
                 |
                 v
          Twilio Voice Call
                 |
                 v
       Flask Webhook Endpoints
                 |
                 v
       Speech / Input Processing
                 |
                 v
      Conversation State Manager
                 |
                 v
       Intent and Query Handling
                 |
          +------+------+
          |             |
          v             v
     Course FAQs    Sales Workflow
          |             |
          +------+------+
                 |
                 v
       AI Response Generation
                 |
                 v
        Voice Response to Student
                 |
                 v
       Preference / Detail Collection
                 |
                 v
         Demo Booking Workflow
                 |
                 v
       Booking Confirmation and
          Data Record Storage
```

*Note: This diagram represents the logical workflow. The exact implementation of speech recognition, response generation, and voice playback depends on the configured Twilio and AI integrations.*

## 🎓 Supported Courses

The current application supports enquiries related to:

* **Python Full Stack Development**
* **Java Full Stack Development**

The conversational workflow can provide relevant course information and help students express their preferences.

Additional courses can be incorporated by extending the application's course information and conversation logic.

## 📂 Project Structure

The following is an illustrative project structure. Adjust the filenames to match your actual repository.

```text
AI_CALL/
│
├── app.py                  # Flask application entry point
├── requirements.txt        # Python dependencies
├── .env                    # Environment variables (not committed)
├── .gitignore              # Git exclusion rules
├── README.md               # Project documentation
│
├── student_bookings.json   # Booking records, if used by your version
│
└── [other modules]         # Additional application components
```

The exact structure may differ depending on how the application separates its Flask routes, Twilio integration, AI logic, and booking functionality.

## ⚙️ How It Works

### Step 1: Initiate a Voice Interaction

Twilio initiates or handles the configured voice call and communicates with the Flask application through webhooks.

### Step 2: Process Student Input

The application receives the student's response through the configured voice interaction workflow.

### Step 3: Maintain Conversation Context

The application tracks relevant conversation information, including the current stage, course interest, and questions already discussed.

### Step 4: Handle Enquiries

The agent processes student questions and provides relevant information about courses, fees, schedules, internships, placements, projects, and certifications.

### Step 5: Guide Course Selection

Based on the conversation, the application helps the student explore the available courses and express their interest.

### Step 6: Collect Demo Preferences

When the student is interested in a demonstration session, the agent collects the relevant details and preferred scheduling information.

### Step 7: Record Booking Information

The application records the collected booking details using its configured storage mechanism and proceeds through the booking confirmation workflow.

## 🚀 Installation and Setup

### Prerequisites

Before running the application, ensure you have:

* Python 3.10 or a compatible version supported by your dependencies.
* A Twilio account with the required voice capabilities.
* A Google AI API key for the configured generative AI integration.
* Git installed on your system.
* A public HTTPS endpoint for receiving Twilio webhooks during development or deployment.

### 1. Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
```

Navigate to the project directory:

```bash
cd AI_CALL
```

Replace the repository URL with your actual GitHub repository URL.

### 2. Create a Virtual Environment

On Windows:

```bash
python -m venv venv
```

Activate the environment:

```bash
venv\Scripts\activate
```

On macOS or Linux:

```bash
source venv/bin/activate
```

### 3. Install Dependencies

If the repository contains a `requirements.txt` file, run:

```bash
pip install -r requirements.txt
```

Otherwise, install the dependencies listed in your application.

For example, the application may require packages such as:

```bash
pip install flask twilio python-dotenv google-generativeai
```

Verify the Google AI SDK package against the import statements used in your implementation.

### 4. Configure Environment Variables

Create a `.env` file in the project root directory and add the configuration values required by your application.

Example:

```env
TWILIO_ACCOUNT_SID=your_twilio_account_sid
TWILIO_AUTH_TOKEN=your_twilio_auth_token
TWILIO_PHONE_NUMBER=your_twilio_phone_number

GOOGLE_API_KEY=your_google_ai_api_key

FLASK_DEBUG=True
```

**Important:** These names are examples. Use the exact environment variable names referenced by your Python code.

Never publish API keys, authentication tokens, or other secrets in a public GitHub repository.

### 5. Start the Flask Application

If your Flask entry point is `app.py`, run:

```bash
python app.py
```

The development server will typically start at:

```text
http://127.0.0.1:5000
```

The exact address and port depend on your Flask configuration.

### 6. Configure Twilio Webhooks

Twilio must be able to reach your Flask webhook endpoints.

For local development, you can expose your application through an HTTPS tunnelling service, such as ngrok.

Configure the appropriate public webhook URL in your Twilio settings.

For example:

```text
https://your-public-domain.example/your-webhook-route
```

Replace the example domain and route with your actual public URL and Flask endpoint.

Ensure that the webhook route and HTTP method match your application's implementation.

## 🔐 Environment Variables

Keep sensitive configuration in environment variables rather than hardcoding it in your source code.

| Variable              | Description                                                            |
| --------------------- | ---------------------------------------------------------------------- |
| `TWILIO_ACCOUNT_SID`  | Twilio account identifier                                              |
| `TWILIO_AUTH_TOKEN`   | Twilio authentication token                                            |
| `TWILIO_PHONE_NUMBER` | Configured Twilio phone number                                         |
| `GOOGLE_API_KEY`      | API key for the configured Google AI service                           |
| `FLASK_DEBUG`         | Controls Flask development debugging, if referenced by the application |

Use production-appropriate configuration and keep debugging disabled in production.

## 💬 Example Conversation

The following is an illustrative conversation showing the intended interaction style, not a transcript from a live call.

**AI Agent:** Hello! Thank you for your interest in our training programs. Are you looking for information about any particular course?

**Student:** I want to learn Python Full Stack Development.

**AI Agent:** Great! I can help you understand the course. Would you like to know about the curriculum, fees, internship opportunities, or placement support?

**Student:** I want to know about placements.

**AI Agent:** I can provide information about the available placement support and related opportunities.

**Student:** Can I attend a demo session?

**AI Agent:** Certainly. I can help you provide your preferred date and time for a demo session.

**Student:** I prefer Saturday afternoon.

**AI Agent:** Thank you. I'll collect the required details and proceed through the demo booking workflow.

The actual responses and booking confirmations depend on the configured course information, AI prompts, and booking implementation.

## 🎯 Use Cases

This project can be adapted for:

* Educational institutes handling course enquiries.
* Training centres automating initial student counselling.
* EdTech businesses managing prospective student interactions.
* Automated course discovery and lead qualification.
* Demo session scheduling and enquiry management.
* Voice-based customer engagement workflows.

## 🔮 Future Improvements

Potential enhancements include:

* **Persistent conversation storage:** Store conversation history in a database for reliable retrieval across sessions.
* **Advanced workflow orchestration:** Introduce a dedicated workflow engine for more complex conversations.
* **CRM integration:** Connect student enquiry and booking records to a customer relationship management platform.
* **Calendar integration:** Check actual availability and schedule confirmed demo appointments.
* **Multilingual support:** Enable conversations in additional languages.
* **Analytics dashboard:** Track enquiry volumes, booking conversion rates, and frequently asked questions.
* **Automated testing:** Add unit tests and integration tests for Flask endpoints, conversation state, and booking workflows.
* **Production deployment:** Deploy the application with secure configuration, monitoring, logging, and appropriate error handling.

These are possible future enhancements and are not necessarily part of the current implementation.

---

⭐ If you find this project useful, consider starring the repository.
