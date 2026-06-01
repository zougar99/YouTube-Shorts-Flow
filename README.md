# 🤖 YouTube Shorts Flow — Automated Shorts Pipeline

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/zougar99/YouTube-Shorts-Flow/blob/main/LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/zougar99/YouTube-Shorts-Flow?style=social)](https://github.com/zougar99/YouTube-Shorts-Flow)
[![Platform](https://img.shields.io/badge/platform-Web%20%7C%20Next.js-black)](https://github.com/zougar99/YouTube-Shorts-Flow)

> **AI-powered automated pipeline** for YouTube Shorts — clips trending content, adds captions, and publishes via OAuth. Built with Next.js, TailwindCSS, and the YouTube Data API v3.

---
## 📖 Table of Contents
- [Features](#-features)
- [How It Works](#-how-it-works)
- [Tech Stack](#-tech-stack)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Usage Guide](#-usage-guide)
- [API Endpoints](#-api-endpoints)
- [Screenshots](#-screenshots)
- [Roadmap](#-roadmap)
- [FAQ](#-faq)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)
- [License](#-license)

---

## ✨ Features
- ✔ **Trend Analysis** — Scans YouTube, TikTok & Twitter for trending clips
- ✔ **Smart Clipping** — AI detects the best moments (peak engagement)
- ✔ **Auto Captions** — Generates subtitles + animated text overlays
- ✔ **OAuth Publishing** — Posts directly to your YouTube channel
- ✔ **Scheduling** — Set daily post limits and time slots
- ✔ **Multi-Language** — Transcribes + captions in 20+ languages
- ✔ **Analytics** — View performance of published Shorts
- ✔ **Queue Management** — Prioritize, review, approve before posting

---

## 🔮 How It Works

```
   Trend Sources         Pipeline Steps           Output
   ┌──────────┐
   │ YouTube  │──┐
   ├──────────┤  │   ┌──────────────┐     ┌──────────────┐
   │ TikTok   │──┼──►│ 1. Analyze   │────►│ 2. Clip      │
   ├──────────┤  │   └──────────────┘     └──────┬───────┘
   │ Twitter  │──┘                              │
   └──────────┘                                 ▼
                                         ┌──────────────┐
                                         │ 3. Caption   │
                                         │ + Overlay    │
                                         └──────┬───────┘
                                                ▼
                                         ┌──────────────┐
                                         │ 4. Queue     │
                                         │ (Review)     │
                                         └──────┬───────┘
                                                ▼
                                         ┌──────────────┐
                                         │ 5. Publish   │
                                         │ (OAuth)      │
                                         └──────────────┘
```

---

## 💻 Tech Stack

| Component | Technology |
|-----------|-----------|
| Frontend | Next.js 14 + TailwindCSS |
| Backend | Next.js API Routes |
| Auth | YouTube OAuth 2.0 |
| AI | OpenAI / Gemini API |
| Database | PostgreSQL (Prisma) |
| Video | FFmpeg |
| Queue | Redis / BullMQ |
| Hosting | Vercel |

---

## 🚀 Installation

```bash
git clone https://github.com/zougar99/YouTube-Shorts-Flow.git
cd YouTube-Shorts-Flow

# Install dependencies
npm install

# Set up environment
cp .env.example .env.local
# Edit .env.local with your keys (see Configuration below)

# Run database migrations
npx prisma migrate dev

# Start dev server
npm run dev
```

---

## 📄 Configuration

Edit `.env.local`:

```env
# YouTube OAuth
YOUTUBE_CLIENT_ID=your_client_id
YOUTUBE_CLIENT_SECRET=your_client_secret
YOUTUBE_REDIRECT_URI=http://localhost:3000/api/auth/callback

# AI API Keys
OPENAI_API_KEY=sk-...
GEMINI_API_KEY=...

# Database
DATABASE_URL=postgresql://user:pass@localhost:5432/shortsflow

# Queue
REDIS_URL=redis://localhost:6379

# Scheduling
DAILY_POST_LIMIT=5
POST_HOURS=9,12,15,18,21
```

---

## 🧰 Usage Guide

### 1. Authenticate
- Visit `/login` and click **Connect YouTube**
- Grant OAuth permissions (manage channel)

### 2. Discover Trends
- Go to **Trends** tab — enter a keyword or category
- AI analyzes top content across YouTube, TikTok, Twitter
- Select clips you want to use

### 3. Queue & Publish
- Review auto-generated clips in the Queue
- Edit captions, trim start/end, add hashtags
- Click **Post** or let the scheduler auto-post

---

## 🌐 API Endpoints

| Method | Route | Description |
|--------|-------|-------------|
| GET | `/api/trends` | Get trending topics |
| POST | `/api/clips` | Create clip from URL |
| GET | `/api/queue` | List queued clips |
| POST | `/api/publish` | Publish a clip |
| GET | `/api/analytics` | Get channel stats |

---

## 🖼 Screenshots

> *(Screenshots coming soon. PRs welcome!)*

| Dashboard | Clip Editor | Analytics |
|-----------|------------|-----------|
| ![Dashboard](.github/screenshots/dashboard.png) | ![Editor](.github/screenshots/editor.png) | ![Analytics](.github/screenshots/analytics.png) |

---

## 🔄 Roadmap

- 🟢 TikTok direct publishing
- 🟡 Instagram Reels support
- ⚫ AI voiceover generation
- ⚫ Music/audio auto-sync
- ⚫ Thumbnail auto-generation

---

## ❓ FAQ

### Is this against YouTube TOS?
No — Shorts Flow uses the official YouTube Data API v3 with proper OAuth. You control what gets posted.

### Can I review before posting?
Yes — all clips go through a Queue for review/editing before publishing.

### Does it require FFmpeg?
Yes — FFmpeg is required for video processing (clipping, captions, overlays).

---

## 🚧 Troubleshooting

| Problem | Solution |
|---------|----------|
| **OAuth fails** | Check redirect URI matches .env.local exactly |
| **Clips not generating** | Verify FFmpeg is installed; check logs/api |
| **Queue not processing** | Is Redis running? Check BullMQ dashboard |
| **Captions out of sync** | Adjust `CAPTION_OFFSET_MS` in .env.local |

---

## 🤝 Contributing

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📐 License
MIT — see [https://github.com/zougar99/YouTube-Shorts-Flow/blob/main/LICENSE](https://github.com/zougar99/YouTube-Shorts-Flow/blob/main/LICENSE)

---

<p align="center">
  Made with 🎬 and ❤️ by <a href="https://github.com/zougar99">zougar99</a>
</p>
