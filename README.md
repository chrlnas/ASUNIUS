# Asunius — AI Generator

A single-file web app for AI **image** and **writing** generation. No build step, no backend, no dependencies — just open `app.html` in a browser.

## Features

- **🎨 Image generation** — via [Pollinations](https://pollinations.ai) (free, unlimited, no API key). Style presets, size, model (Flux/Turbo), optional seed.
- **✍️ Writing generation** — via the Claude API if you add a key, or a lightweight local template generator if you don't.
- **📚 History** — every generation saved locally in `localStorage` (up to 100), with thumbnails, detail view, delete, and JSON export.
- **⚙️ Settings** — Claude API key (stored only in your browser), light/dark theme, save-to-history toggle, export.
- **🌍 Bilingual** — English and Bahasa Indonesia, selectable from the top bar or Settings. The AI responds in the selected language.

## Usage

1. Open `app.html` in any modern browser.
2. Go to **Generate**, type a prompt, pick image or writing mode, and hit **Generate**.
3. (Optional) For richer writing, add a Claude API key in **Settings**.

## Notes

- The Claude API call goes directly from your browser to Anthropic using the `anthropic-dangerous-direct-browser-access` header. The key is stored only in `localStorage` and never sent anywhere except Anthropic. Don't embed the key in a shared URL.
- Image style labels are mapped to English keywords before being sent to the image model, since diffusion models are trained mostly on English captions — so non-English users still get good results.
- Everything (history, key, theme, language) is stored locally in the browser. Clearing site data resets the app.

## Tech

Single self-contained HTML file — inline CSS and JS, no external libraries, no build tooling.
