# Resume Tailor

A single-page web app that tailors your résumé to a specific job ad — **honestly**. It only rewords and reorders what you actually wrote; it never invents skills, metrics, titles, or experience.

## What it does

- Paste your résumé and a job description (no link needed) + optional company name.
- Get an honest **match score**, the keywords you already match, and the ones the ad wants that you don't clearly show.
- See **rewrites of your real bullets** in the ad's language — each shown next to the original line you wrote, with a note confirming it's a faithful rewording.
- Under each missing keyword / gap, add any **real experience you forgot** to include, then **Re-analyze** to fold it in.
- **Download** a complete, single-column, **ATS-friendly `.docx`** résumé built from your real facts and the rewrites you selected.

## Setup

The app calls the **Anthropic (Claude) API** directly from your browser.

1. Create an API key at [console.anthropic.com/settings/keys](https://console.anthropic.com/settings/keys) and add credits under Billing. (This is separate from a Claude.ai chat subscription.)
2. Open `index.html` in your browser.
3. Paste your key — it's stored only in your browser's local storage and is sent only to Anthropic's API.

## Honesty guardrails

The app's instructions to the model forbid inventing anything. "Helped with X" is never upgraded to "Led X"; requirements you can't support are listed as gaps, not turned into fake bullets. Always proofread the generated `.docx` before sending it.

## Tech

Plain HTML/CSS/JS, no build step. Word export uses [`docx`](https://github.com/dolanmiu/docx) loaded from a CDN.
