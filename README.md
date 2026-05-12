#YouTube-Shorts-Flow


![Downloads](https://img.shields.io/github/downloads/YOUR_USER/YOUR_REPO/total?style=for-the-badge&logo=download&logoColor=white)

Automatisation YouTube — monitor, clip, publish Shorts.

- **Chain analysis**: YouTube Data API (vues, trend) ou RSS fallback
- **Cutting plan Shorts**: automatic segmentation into segments ≤ 60s
- **Publication auto**: yt-dlp + ffmpeg → upload via OAuth YouTube
- **Manual publishing**: copy/paste title + description
- **Extension Firefox**: popup with quick copy and upload prefill
- **OAuth YouTube**: secure connection with refresh token

##Startup

```bash
npm run dev
```

Open[http://localhost:3000](http://localhost:3000).

##Configuration

Copy`.env.example` → `.env.local`and informs:
- `GOOGLE_CLIENT_ID` / `GOOGLE_CLIENT_SECRET` / `GOOGLE_REDIRECT_URI`
- `YOUTUBE_API_KEY`(optional, otherwise RSS fallback)

##Structure

```
app/          – Routes Next.js (pages + API)
components/   – Composants React
lib/ – Business logic (analysis, OAuth, clip, template, etc.)
extension/ – Firefox module for the Shorts plan
scripts/ – Utilities
```
