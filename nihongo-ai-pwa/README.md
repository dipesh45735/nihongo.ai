# Nihongo AI — Offline-first Japanese learning PWA

A lightweight mobile-first Progressive Web App for beginner Japanese learners. Includes Hindi and English explanations, local lessons, flashcards, quizzes, progress tracking, IndexedDB persistence, export/import, and service-worker caching.

## Features
- Responsive UI designed for small Android screens.
- Six starter lessons covering Hiragana vowels, greetings, introductions, numbers, は particle, and Katakana.
- Vocabulary flashcards with Hindi and English meanings.
- Multiple-choice quiz with explanations and score history.
- Local progress persistence with IndexedDB (localStorage fallback).
- Export/import progress JSON backup.
- PWA manifest and service worker for offline app-shell caching.
- No account, paid API, or API key required.

## Run locally
Service workers and installable PWAs require a secure context (HTTPS or localhost). Do **not** open `index.html` directly using a `file://` URL if you want service-worker/offline installation to work.

### Option A: Python
1. Install Python 3 if needed.
2. In this folder, run:
   ```bash
   python -m http.server 8000
   ```
3. Open `http://localhost:8000` in your browser.

### Option B: Node.js
If Node.js is installed, you can use any static server, e.g.:
```bash
npx serve .
```

## Publish free
Upload these files to a GitHub repository and enable GitHub Pages in the repository settings. The app uses relative paths so it can work from a project subpath. Hosting free-tier terms and availability may change.

After publishing:
1. Open the HTTPS site on your Android phone.
2. Open the browser menu and choose **Add to Home screen** or **Install app** if available.
3. Open the app once while online so the service worker can cache its core files.
4. Then enable airplane mode and test navigation, lessons, quizzes and saved progress.

## Important offline notes
- The app shell and included lesson data are cached locally after the first successful load.
- Browser storage can be cleared by the user or evicted by the browser; use **Export my progress** regularly for backups.
- Google Fonts are optional decorative enhancements; the app uses system fallbacks if fonts are unavailable.
- This version does not include online AI chat or speech scoring. Those need a separate service and are intentionally omitted to keep the starter app free and offline-first.
- This is a starter project. Test installability and offline behaviour on the target browser/Android version before relying on it.

## Update cache
When publishing a new release, change `CACHE_NAME` in `sw.js` (e.g. `nihongo-ai-v2`) so the service worker refreshes cached app files.
