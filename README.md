# Charlamos

Spanish conversation practice that runs on your phone. A native-speaker tutor (Spain, Mexico or
Argentina) stays in character, listens to you through the microphone, talks back, corrects your
mistakes and keeps a notebook of them.

It is a single static page. It calls the Claude API straight from the browser with **your own
Anthropic API key**, which is stored only on the device. Nothing is sent anywhere except
`api.anthropic.com`.

## Files
- `index.html` — the whole app
- `manifest.webmanifest`, `sw.js`, `icon*.png`, `icon.svg` — make it installable to the home screen

## Host it (GitHub Pages, free)
1. Create a repository (public or private) and push this folder to it.
2. Settings → Pages → Source: *Deploy from a branch*, branch `main`, folder `/ (root)`.
3. Open the published URL on your phone in Safari (iPhone) or Chrome (Android).
4. **iPhone:** keep using it in Safari. Add it to Favorites or the start page. Do not use
   *Add to Home Screen*: iOS does not allow speech recognition inside home-screen web apps,
   so the mic is dead there (typing still works).
   **Android:** Chrome menu → *Add to Home screen* works fully, mic included.

Any static host works (Vercel, Netlify, Cloudflare Pages). It must be served over **https** or the
browser will not allow the microphone.

## First run
1. Create an API key at https://platform.claude.com/ and set a monthly spending limit on it.
2. In the app, tap the gear, paste the key, pick scenario, level and region. Done.
3. Tap the mic, speak Spanish, pause. The tutor replies out loud and listens again.

## Cost
Each turn sends the conversation so far plus a short system prompt and gets a short reply back.
With Claude Opus 5.5 that is typically under one cent per turn; with Claude Haiku 5.5 it is a
small fraction of that. The notebook shows the running spend for the current conversation.

## Notes
- Speech recognition is the browser's own (Apple's on iPhone, Google's on Android). Spanish
  dictation works best if a Spanish keyboard or dictation language is installed.
- Better Spanish voices on iPhone: Settings › Accessibility › Spoken Content › Voices › Spanish.
- The key sits in the browser's local storage on that device. Anyone with the unlocked phone could
  read it, so use a dedicated key with a spending cap.
