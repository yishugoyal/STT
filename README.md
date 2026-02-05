# 🦙 OpenAI whisper-large-v3 API

A lightweight, **serverless API** for interacting with **OpenAI whisper-large-v3** via the **Hugging Face Inference API**, deployed on **Cloudflare Workers**. A Speech To Text Model directly integrate with hugging face. 

> Developed by [Yishu Goyal](https://yishu.vercel.app)
> 🚀 Live Demo: [https://stt.yishugoyal.workers.dev/](https://stt.yishugoyal.workers.dev/?q=) 

---

## 🌟 Features

* ✅ Supports both `GET` and `POST` HTTP methods
* 🧠 Integrates **OpenAI whisper-large-v3** model via Hugging Face
* ⚡ Serverless, fast, and scalable using **Cloudflare Workers**
* 🔐 Secure API key management via **environment variables**
* 💬 Returns **JSON-formatted** responses with developer signature
* 🧩 Robust error handling with clear messages

---

## 📦 Project Structure

```
llama3.1-api/
│
├── src/
│   └── index.js                
├── LICENSE             
├── README.md           
└── package.json        
```

---

## 🚀 Quick Start

### 1. GET Request

```
https://stt.yishugoyal.workers.dev/
```

### 2. POST Request

```bash
curl -X POST https://stt.yishugoyal.workers.dev/ \
  -H "Content-Type: audio/flac" \
  --data-binary "@sample.flac"
```
```python
import requests

API_URL = "https://stt.yishugoyal.workers.dev/"

with open("audio.wav", "rb") as f:
    audio_bytes = f.read()

headers = {
    "Content-Type": "audio/wav"
}

response = requests.post(API_URL, data=audio_bytes, headers=headers)

print(response.json())
```

### 3. Sample Response

```json
{
  "reply": "Quantum computing uses qubits...",
  "model":"Llama-3.1-8B",
  "dev": "YishuGoyalCGC"
}
```

---

## 🛠️ Deployment

1. **Install Wrangler CLI**

```bash
npm install -g wrangler
```

2. **Login**

```bash
wrangler login
```

3. **Set Environment Variable**

```bash
wrangler secret put HF_API_KEY
```

4. **Publish**

```bash
npx wrangler publish
```

---

## 🔒 Security Best Practices

* Never commit your **Hugging Face API key** to GitHub
* Always use environment variables (`env.HF_API_KEY`)
* License your code to protect your ownership

---

## 📄 License

**All Rights Reserved © 2025 — Yishu Goyal**

This project is the intellectual property of **Yishu Goyal**.
Unauthorized copying, modification, distribution, or use is strictly prohibited.

---

## 🧑‍💻 Developer
**Yishu Goyal**  
🌐 Portfolio: [yishu.vercel.app](https://yishu.vercel.app)  
💼 LinkedIn: [linkedin.com/in/yishugoyal](https://linkedin.com/in/yishugoyal)  
🐙 GitHub: [github.com/yishugoyal](https://github.com/yishugoyal)  
📧 Email: [yishugoyalbth@gmail.com](mailto:yishugoyalbth@gmail.com)

---

## 💡 Use Cases

* Chatbots & AI assistants
* Microservices backend for LLMs
* Prototyping conversational AI tools
* Educational / demo purposes

