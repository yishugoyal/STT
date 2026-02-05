# 🎙️ Whisper Large v3 – Speech-to-Text API

A **lightweight, serverless Speech-to-Text (STT) API** powered by **OpenAI Whisper Large v3**, deployed on **Cloudflare Workers** and integrated with the **Hugging Face Inference API**.

This API accepts **raw audio files** and returns accurate transcriptions in **JSON format**, making it ideal for real-time and scalable AI applications.

> Developed by **Yishu Goyal**
> 🌐 Live API: [https://stt.yishugoyal.workers.dev/](https://stt.yishugoyal.workers.dev/)

---

## 🌟 Features

* 🎧 **Speech-to-Text** using **Whisper Large v3**
* ⚡ **Serverless & ultra-fast** (Cloudflare Workers)
* 🔐 Secure **API key management** via environment variables
* 📦 Accepts **raw audio bytes** (`wav`, `mp3`, `flac`)
* 🌍 **CORS enabled** (browser & mobile friendly)
* 🧠 Clean **JSON responses**
* 🛡️ Robust error handling

---

## 📦 Project Structure

```
whisper-stt-api/
│
├── src/
│   └── index.js        # Cloudflare Worker
├── README.md
├── package.json
└── LICENSE
```

---

## 🚀 API Usage

### Endpoint

```
POST https://stt.yishugoyal.workers.dev/
```

> ❗ Only `POST` requests are supported
> ❗ Send **raw audio bytes**, not multipart/form-data

---

## 🎧 Example Requests

### Using `curl`

```bash
curl -X POST https://stt.yishugoyal.workers.dev/ \
  -H "Content-Type: audio/flac" \
  --data-binary "@sample.flac"
```

---

### Using Python

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

---

### Using JavaScript (Node.js)

```js
import fs from "fs";

const audio = fs.readFileSync("audio.wav");

const res = await fetch("https://stt.yishugoyal.workers.dev/", {
  method: "POST",
  headers: {
    "Content-Type": "audio/wav",
  },
  body: audio,
});

console.log(await res.json());
```

---

## 📤 Sample Response

```json
{
  "text": "Hello, this is a speech to text transcription.",
  "model": "whisper-large-v3",
  "dev": "YishuGoyalCGC"
}
```

---

## 🛠️ Deployment (Cloudflare Workers)

### 1️⃣ Install Wrangler

```bash
npm install -g wrangler
```

### 2️⃣ Login

```bash
wrangler login
```

### 3️⃣ Set Hugging Face API Key

```bash
wrangler secret put HF_API_KEY
```

### 4️⃣ Deploy

```bash
wrangler publish
```

---

## 🔒 Security Notes

* 🔑 Never commit API keys to GitHub
* 🧪 Use `wrangler secret` for production secrets
* 🚫 No audio files are stored on the server

---

## 💡 Use Cases

* 📞 Call transcription & analysis
* 🎧 Voice notes → text
* 🤖 Voice input for LLM pipelines
* 🛡️ Scam / fraud detection preprocessing
* 📱 Mobile STT features
* 🧪 AI & ML experiments

---

## 📄 License

**All Rights Reserved © 2025 — Yishu Goyal**

This repository and its contents are the exclusive intellectual property of **Yishu Goyal**.
Unauthorized copying, modification, redistribution, or commercial use is strictly prohibited.

---

## 👨‍💻 Developer

**Yishu Goyal**
🌐 Portfolio: [https://yishu.vercel.app](https://yishu.vercel.app)
💼 LinkedIn: [https://linkedin.com/in/yishugoyal](https://linkedin.com/in/yishugoyal)
🐙 GitHub: [https://github.com/yishugoyal](https://github.com/yishugoyal)
📧 Email: [yishugoyalbth@gmail.com](mailto:yishugoyalbth@gmail.com)

---

## 🚀 What’s next?

If you want, I can also:

* 🔁 Add **STT → LLaMA → Fraud Score** pipeline README
* 📊 Add **API rate-limit & performance section**
* 🧪 Add **Postman collection**
* 📱 Add **Android / iOS usage examples**

Just say the word 😄
