# Sitges — The Living Guide

A static, AI-enhanced travel guide to Sitges, Catalonia. Built with plain HTML, CSS, and JavaScript — no build step, ready to deploy anywhere.

## Features

- **Three living modes** — Day, Sunset, and Festival — each shifting the entire palette and hero animation to match Sitges' personality at different times.
- **Beach, culture, festival, and food guides** with real local info.
- **Local AI Assistant** — an optional chat panel that calls the Anthropic Claude API directly from the browser. Visitors enter their own API key (stored only in `localStorage`/session, never transmitted anywhere but Anthropic) and get personalized recommendations.

## Running locally

No build tools needed. Just open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Deploying to GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Set source to the `main` branch, root folder.
4. Your site will be live at `https://<username>.github.io/<repo-name>/`.

## Using the AI Assistant

The assistant feature requires an [Anthropic API key](https://console.anthropic.com/). Enter it in the "Ask the Local AI" section. The key is used client-side only to call `api.anthropic.com` directly — it is never sent to any server other than Anthropic's, and is not persisted beyond the browser session.

**Note:** Calling the Anthropic API directly from a static site exposes your API key in the browser's network requests. For a public-facing production deployment, consider routing requests through a small backend proxy to keep your key private.

## File structure

```
index.html        Main page
assets/style.css   Styles & theming (day/sunset/festival)
assets/script.js   Mode switching + AI assistant logic
```

## License

Free to use and adapt.
