# 🎬 MP4 to Audio → Transcription & Accent Analysis (n8n Workflow)

This project contains a complete n8n workflow that accepts an MP4 video URL, extracts the audio, transcribes the speech, and uses AI to analyze the speaker's English accent.

---

## 📌 Features

- ✅ Accepts public MP4 URLs (e.g., from YouTube, Loom, direct links)
- 🎧 Converts video to audio using FreeConvert API
- ✍️ Transcribes speech with OpenAI Whisper
- 🧠 Classifies English accent via GPT-4 with confidence scoring
- 💬 Optional chatbot interface to drop in video links
- 🔁 Can be triggered manually or by other workflows

---

## 🧠 How It Works

1. **Input**: You send an MP4 video URL (e.g. through chatbot or trigger).
2. **Regex Extraction**: The system detects and validates video URLs.
3. **Upload & Convert**: The video is uploaded to FreeConvert and converted to MP3.
4. **Transcription**: OpenAI Whisper transcribes the audio to text.
5. **Analysis**: A custom GPT-based prompt identifies the speaker's accent, confidence score, and a short explanation.
6. **Output**: JSON result with:
   - `Accent`: e.g., "American English"
   - `Confidence`: e.g., "91%"
   - `Summary`: Linguistic cues from transcript

---

## 🚀 Try It With These Sample Videos

- [Tears of Steel (MP4)](https://storage.googleapis.com/gtv-videos-bucket/sample/TearsOfSteel.mp4)
- [Volkswagen GTI Review (MP4)](https://storage.googleapis.com/gtv-videos-bucket/sample/VolkswagenGTIReview.mp4)

---

## 🛠️ Setup Requirements

- [x] An n8n instance (self-hosted or cloud)
- [x] FreeConvert API Key
- [x] OpenAI API Key with Whisper and GPT access
- [x] Optional: Chatbot UI (via `chatTrigger` node)

---

## 📦 Installation

1. Import the JSON workflow into your n8n instance
2. Set your credentials for:
   - FreeConvert API
   - OpenAI API
3. Trigger the workflow:
   - Via webhook
   - From a chat
   - Or from another workflow

---

## ✨ Example Output

```json
{
  "Accent": "British English",
  "confidence_in_English": "88%",
  "summary": "The speaker consistently uses British spelling and intonation markers typical of Received Pronunciation."
}
