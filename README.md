# What Can I Watch Next

An interactive prototype for a detailed-rating model for streaming recommendations.

Pick what you have loved, say what it was about them that worked, name your mood, and get a list
worth trying plus a read on the kind of viewer you are.

## Running it

It is a single self-contained HTML file. Open `index.html` in a browser, or drop the folder into a
GitHub repository and switch on GitHub Pages. There is no build step, no server, no dependencies
and no API keys.

## How to publish it on GitHub Pages

1. Create a new public repository on github.com.
2. Upload `index.html` and this README (drag and drop works, use "uploading an existing file").
3. Settings, then Pages, then set Source to "Deploy from a branch", branch `main`, folder `/ (root)`.
4. Wait a minute. The site appears at `https://<your-username>.github.io/<repo-name>/`.

## What is inside

- **477 titles**, hand-tagged against a nine-axis rating framework.
- **Synopses** for every title, adapted from Wikipedia, CC BY-SA 4.0.
- **Official title logos and stills** for 301 of them, from Wikimedia Commons, each licence-checked
  individually and credited in the footer. Embedded directly in the page, so nothing is hotlinked.
- **A live layer** that queries Wikidata (CC0) at results time for titles newer than the catalogue,
  so the tool stays current without maintenance.

## How the scoring works

    taste = 0.60·category match + 0.25·genre affinity + 0.15·viewing shape
    (with no shape selected: 0.70·category + 0.30·genre)
    mood list = 0.50·taste + 0.50·mood fit, mood-matching titles only

Picking a title alone contributes its own attributes at 0.3 weight, so recommendations still work
for someone who rates nothing. Ticking a category weights that whole category; ticking a specific
detail weights it at 1.6 and its parent category at 0.4.

The engine is deliberately deterministic arithmetic. No embeddings, no collaborative filtering, no
model, no LLM at run time, so every recommendation can be read and argued with. Each card names the
attribute that earned it and the title it was said about.

## Privacy

Everything runs in the browser. No accounts, no analytics, no tracking. An uploaded watch history
is parsed locally and never transmitted. Answers are kept in `localStorage` on the visitor's own
device so they can return and change their mood without starting over.

## Credits

Synopses adapted from Wikipedia (CC BY-SA 4.0). Title logos and stills from Wikimedia Commons,
individually licensed and credited in the page footer. Live title data from Wikidata (CC0).
