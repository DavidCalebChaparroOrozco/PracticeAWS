## What is a chatbot?

It's an artificial intelligence program designed to hold conversations with people, either by text or voice.

Its goal is to understand what the user says, process it, and respond helpfully, mimicking a human conversation.

Examples:
- Customer Service
- Automating repetitive tasks
- Personal assistants
- Marketing and sales.

---

## Rule-Based Chatbots

A rule-based chatbot is a type of chatbot that operates by following predefined instructions with fixed menus, buttons, keywords, and conversation flows.

It can only respond to what it was specifically programmed to do.

**How ​​they work:** They follow predetermined flows, relying on keywords, menu options, or frequently asked questions. They don't understand natural language, only what is programmed.

**Advantages:**
- Predictable
- Easy to implement
**Disadvantages:**
- They don't understand natural phrases
- They don't adapt to language variations.

---

## Chatbot with Artificial Intelligence

An AI chatbot is a digital assistant capable of understanding human language, interpreting complex questions, and generating natural responses using advanced artificial intelligence models like those offered by Amazon Bedrock.

**Main Features:**
- Understands natural language.
- Responds like a real person.
- Interprets intent and context.
- Learns from provided content (PDFs, websites, documents).
- Handles open and unstructured conversations.
- Can maintain continuity ("memory") during the dialogue.

---

## How does the chatbot work?

- The user types or speaks a question.
- The chatbot analyzes the message and finds the best answer (based on rules or artificial intelligence).

- It returns an immediate, relevant, and 24/7 response.

**There are 2 main types:**
- Rule-based chatbots
- Chatbots with artificial intelligence.

---

## AWS Services

### Amazon Bedrock
Amazon's service for using advanced generative artificial intelligence models (LLMs) without the need for training or infrastructure management.

**Main functions:**
- Summarizing, explaining, and translating
- Querying knowledge bases
- Business assistants with custom documents
- Bots that require creativity and natural responses.

### Amazon Lex

It's Amazon's service specializing in creating chatbots with conversational artificial intelligence.

**Main features:**
- Natural language processing (NLP)
- Speech-to-text recognition
- Creation of intents, slots, and dialogues
- Direct integration with Lambda

**Ideal for chatbots:** On websites, mobile apps, and in contact centers.

**It is based on 4 fundamental pieces**

- Intents:
  - Example: Check a schedule
- Required data (Slots)
  - Recognizing that we will need context to provide that answer
- User Expressions (Utterances)
  - Phrases that the user can enter. Example: What are the opening hours? / What time do you open?
- Final action (Fulfillment)
  - Example: Confirm the operation, show the response

### Amazon Polly

It's a text-to-speech service that converts text into natural human speech in multiple languages ​​and tones.

**Main features:**
- Convert text to natural speech
- Realistic voices in multiple languages
- Customizable tone, rhythm, and style

**Ideal for:**
- Voicebots
- Reading chatbot responses
- Virtual voice assistants

### Amazon Transcribe
It's an automatic **speech-to-text service that accurately converts audio** to text in real time.

**Main features:**
- Real-time conversion of posts to text
- Speaker identification (speaker diarization)
- Accurate transcription in multiple languages

**Ideal for:**
- Voice bots (Alexa, call centers)
- Capturing what customers say during calls
- Assistants that receive audio input.

### AWS Lambda
It's a serverless computing service that automatically executes your code **when an event occurs**, eliminating the need to manage infrastructure.

**Main features:**
- Run chatbot logic on servers
- Perform validations, calculations, or dynamic responses
- Connect to APIs, databases, or CRMs

**Ideal for:**
- Chatbots requiring custom logic
- Integrations with enterprise systems
- Scalable, low-cost chatbots

