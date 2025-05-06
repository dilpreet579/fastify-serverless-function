# OpenAI-Realtime-API Backend

The OpenAI-Realtime-API is a Node.js backend that acts as a real-time bridge between Twilio phone calls and OpenAI's Realtime API (e.g., GPT-4o), enabling AI-powered voice interactions, appointment scheduling, and webhook integrations for customer service automation.

---

## 🚀 Features
- Real-time audio streaming from Twilio to OpenAI Realtime API
- AI-powered conversation and transcription
- Dynamic system prompt (SYSTEM_MESSAGE) configurable via API
- WebSocket and REST API endpoints
- Webhook integration for structured data delivery (e.g., to Make.com)
- High-performance Fastify server

---

## 🛠️ Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/dilpreet579/fastify-serverless-function.git
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Configure Environment Variables
Create a `.env` file in the root directory:
```env
OPENAI_API_KEY=your_openai_api_key
WEBHOOK_URL=https://your.webhook.url/endpoint
PORT=3001
```
- `OPENAI_API_KEY`: Your OpenAI API key with access to the Realtime API
- `WEBHOOK_URL`: (Optional) Endpoint to receive structured call data
- `PORT`: (Optional) Port to run the server (default: 3001)

### 4. Start the Server
```bash
node index.js
```

---

## 🔌 API Endpoints

- `GET /` — Health check
- `GET /test-webhook` — Sends a test payload to your webhook
- `ALL /incoming-call` — Twilio webhook endpoint for incoming calls
- `GET /media-stream` — WebSocket endpoint for real-time audio streaming
- `GET /system-message` — Returns the current SYSTEM_MESSAGE prompt
- `POST /system-message` — Updates the SYSTEM_MESSAGE prompt (expects `{ systemMessage: "..." }` JSON body)

---

## 🤖 Integration with VocaAI Website
- The VocaAI website (frontend) configures the system prompt via the `/system-message` endpoint
- All new calls and sessions use the latest prompt set via API
- Designed for seamless integration with Next.js and modern web frontends

---

## 📁 Project Structure
- `index.js` — Main server and route definitions
- `openai.service.js` — OpenAI API, audio processing, and webhook logic
- `counter.js` — (Optional) Call counter logic
- `.env` — Environment variables (not committed)

---

## 🧩 Dependencies
- fastify, @fastify/websocket, @fastify/formbody
- ws
- dotenv
- axios
- express, express-ws (legacy/optional)

---

## 🧪 Usage & Testing
- Ensure your `.env` is configured and the server is running
- Use the VocaAI website or API tools (e.g., Postman) to update the system prompt
- Initiate Twilio calls to test real-time AI conversations
- Webhook will receive structured data after each call (if configured)

---

## 🚀 Deployment
- Deploy on any Node.js-compatible server or cloud platform
- Ensure all environment variables are set in your deployment environment
- Expose the correct port and secure your API endpoints as needed

---

## 🤝 Credits
- Built by Dilpreet Singh
- Powered by Node.js, Fastify, OpenAI, and Twilio

---

## 📄 License
ISC

---

**Note:** This project is intended for research, prototyping, or demonstration purposes. For production, add authentication, HTTPS, and robust error handling.
