# 🎙️ Audio Diary – Obsidian Plugin

An Obsidian plugin that lets you record or upload audio, transcribe it using `whisper.cpp`, and generate diary-style summaries using LLMs. Perfect for journaling, memory tracking, or emotional self-reflection.

---

## ✨ Features

- 🔊 Audio file selection from your vault
- 🤖 Local transcription using [whisper.cpp](https://github.com/ggerganov/whisper.cpp)
- 🧠 Summarization and insight extraction via LLM (OpenAI or other)
- 📝 Auto-inserts results into your Daily Notes or a custom path
- 📁 Output in clean Markdown format with metadata (mood, topics, tasks)

---

## 🧩 Plugin Structure

```
audio-diary/
├── main.ts               # Plugin entry point
├── manifest.json         # Obsidian plugin manifest
├── settings.ts           # Settings UI and state
├── whisper.ts            # Handles local Whisper transcription
├── summarizer.ts         # LLM-based summary generation
├── whisper/              # Local build of whisper.cpp + models
│   ├── main              # Compiled whisper binary
│   └── models/
│       └── ggml-base.en.bin
└── styles.css            # Optional CSS
```

---

## 🔧 Setup Instructions

### 1. Clone the Plugin

```bash
git clone https://github.com/yourusername/obsidian-audio-diary
cd obsidian-audio-diary
```

### 2. Build `whisper.cpp`

```bash
git clone https://github.com/ggerganov/whisper.cpp
cd whisper.cpp
make
./models/download-ggml-model.sh base.en
```

Then copy the binary and model into your plugin folder:

```bash
cp whisper.cpp/main audio-diary/whisper/
cp whisper.cpp/models/ggml-base.en.bin audio-diary/whisper/models/
```

### 3. Install Dependencies

```bash
npm install
npm run build
```

### 4. Load the Plugin

- Copy the `audio-diary/` folder into `.obsidian/plugins/` inside your vault
- Enable **Audio Diary** from Obsidian’s Community Plugins tab

---

## 🗣️ Usage

1. Drop a `.wav` or `.mp3` file into your Obsidian vault (default path: `recordings/today.wav`)
2. Run `Process Audio Diary` from the command palette
3. Your transcript and AI summary will be inserted into the current day's note (or another configured path)

---

## ⚙️ Settings

- **Audio file path**: where the plugin looks for your recorded audio file
- **OpenAI API key**: (optional) if you want to use OpenAI for summarization

---

## 📦 Future Ideas

- In-app audio recording
- Sentiment timeline graphs
- Whisper model switching
- Local LLM integration (e.g., Llama.cpp or Ollama)

---

## 🧠 Credits

- [whisper.cpp](https://github.com/ggerganov/whisper.cpp) by Georgi Gerganov
- [OpenAI GPT](https://openai.com/gpt)
- Plugin boilerplate based on Obsidian sample plugin

---

## 🪪 License

MIT License
