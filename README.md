# How to Set Up n8n Workflow for Luxury Watch Leads

This project is a complete automated lead processing workflow built with [n8n](https://n8n.io).  
It processes contact form submissions, validates them, summarizes messages with an LLM, logs leads in Google Sheets, sends Telegram alerts, and updates a watch interest database.

---

## 🔑 1. Insert your API keys

- **DeepSeek (or OpenAI) API**: Register at [deepseek.com](https://deepseek.com), generate an API key, and add it to your LLM node.
- **Google Sheets JSON Key**: In n8n, go to *Credentials* → *Google Sheets*, and add your Google service account key.
- **Telegram Bot Token**:
  - Create a bot via [@BotFather](https://t.me/BotFather)
  - Get your chat ID using [@userinfobot](https://t.me/userinfobot)
  - Add token in *Credentials* → *Telegram*

---

## 🌐 2. Get your Webhook URL

- Open your workflow in n8n.
- Select the **Webhook Trigger** node.
- Click **Activate** → copy the production webhook URL.

---

## 🧪 3. How to test

### ✅ Test with valid input:
```bash
curl -X POST https://<your-webhook-url> \
  -H "Content-Type: application/json" \
  -d '{"name":"Anna","email":"anna@mail.ru","message":"Интересует Rolex Submariner"}'
