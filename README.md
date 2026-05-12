# YouTube-Shorts-Flow

Automatisation YouTube — monitor, clip, publish Shorts.

- **Analyse chaîne** : YouTube Data API (vues, trend) ou RSS fallback
- **Plan découpe Shorts** : segmentation automatique en segments ≤ 60s
- **Publication auto** : yt-dlp + ffmpeg → upload via OAuth YouTube
- **Publication manuelle** : copier/coller titre + description
- **Extension Firefox** : popup avec copie rapide et préremplissage upload
- **OAuth YouTube** : connexion sécurisée avec refresh token

## Démarrage

```bash
npm run dev
```

Ouvre [http://localhost:3000](http://localhost:3000).

## Configuration

Copie `.env.example` → `.env.local` et renseigne :
- `GOOGLE_CLIENT_ID` / `GOOGLE_CLIENT_SECRET` / `GOOGLE_REDIRECT_URI`
- `YOUTUBE_API_KEY` (optionnel, sinon fallback RSS)

## Structure

```
app/          – Routes Next.js (pages + API)
components/   – Composants React
lib/          – Logique métier (analyse, OAuth, clip, template…)
extension/    – Module Firefox pour le plan Shorts
scripts/      – Utilitaires
```
