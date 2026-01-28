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

### Amazon DynamoDB
It's a fully managed NoSQL database designed for speed, scalability, and low latency, ideal for applications requiring millisecond responses, such as chatbots.

**Main features:**
- Saving conversation state
- Storing users, preferences, or history
- High speed and scalability

**Ideal for:**
- Chatbots requiring context between messages
- Recommendation systems within the bot
- Long or personalized conversations

### Amazon API Gateway
**It's a fully managed service** that lets you **create, publish, secure, and monitor APIs** that connect your applications to your backend services, such as Amazon Lambda or Amazon Bedrock.

**Main features:**
- Create REST endpoints for chatbots.

- Connect the frontend (web/app) to Lambda or Bedrock.

- Manage security, throttling, and CORS.

**Ideal for:**
- Web chatbots with API calls
- Integrating backend with frontend
- Multichannel chatbots

### Amazon S3
It's a highly scalable and durable **object storage** service where you can store files such as images, PDFs, audio, catalogs, and any other content your chatbot needs.

**Main features:**
- Store files, documents, or logs
- Store resources for knowledge bases
- Integrate documents into the bot using Bedrock Edition

**Ideal for:**
- Chatbots that use their own information
- Store documents for RAG (Resource Analysis Group)
- Store files submitted by the user

---

## Practical example
### Amazon Lex
- Traditional
- IAM Permissions: Create a role with basic Amazon Lex permissions
- Lex Error Logging: Enabled / Disabled
- Idle Session Timeout: 5 min - Select the bot name and go to All Languages
- Add a language
- Add an existing language
- Wait for the bot to be created
- Then return to where you created the bot and select Intents
- Add a basic one, for example, "Greeting"
- Contexts: You can add as many as you want
- In the initial response, this is what you want the bot to say.

---

## Benefits
- Continuous support without requiring on-site staff
- Reduced operating costs
- Consistent and standardized responses
- Immediate scalability to meet increased demand
- Easy integration with other systems

## Basic Security for Chatbots on AWS

- Use of minimal permissions (IAM) to control access
- Data encryption in S3 and secure communications
- API protection with keys or Amazon Cognito
- Monitoring with CloudWatch to detect errors and unusual activity