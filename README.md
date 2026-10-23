# Swipestorm

Tinder-style brainstorming on anything. Say what you're ideating, swipe the cards an AI deals you, and get a finished **brief, plan, build spec or handoff prompt**.

- **Right**: keep · **Left**: drop · **Up**: must-have · **Down**: decide later
- A goal meter fills as each part of the plan (the AI's "slots") gets covered
- A practical ↔ creative slider controls how bold the cards are
- The result is always a short summary, your folded card lists, and the output you picked
- **Refine** a finished session: deal more cards (or none), change the output type, and say what to focus on
- **Share** the result (your phone's share sheet, or copy), **download** it as Markdown, and find recent sessions again on the start screen (saved in this browser only)
- English and Hungarian interface (EN/HU toggle, top right). It switches to Hungarian by itself when you type the topic in Hungarian; the cards and output follow the topic's language

**Try it: [swipestorm.tmsso.com](https://swipestorm.tmsso.com)**

It's one HTML file with no build step and no dependencies.

## Three ways to run it

The page detects where it is running and picks the AI connection by itself.

### 1. Inside Claude (uses your Claude plan, no key)

Open a chat in [Claude](https://claude.ai), attach `index.html` and ask:

> Publish this file as an artifact with the `sample` capability.

When it runs as a Claude artifact, the page uses the viewer's own Claude account. The first time you deal cards, Claude asks for permission.

### 2. Bring your own key (GitHub Pages or a local file)

Open [swipestorm.tmsso.com](https://swipestorm.tmsso.com), or download `index.html` and open it in a browser. Under **AI connection**, pick one:

| Option | Key | Default models (you can edit them) |
|---|---|---|
| Anthropic | [console.anthropic.com](https://console.anthropic.com/settings/keys) | `claude-haiku-5-5` for cards, `claude-sonnet-5-5` for the output |
| OpenRouter | [openrouter.ai/keys](https://openrouter.ai/keys) | `anthropic/claude-haiku-5.5`, `anthropic/claude-sonnet-5.5`; any OpenRouter model works |

Press **Test connection** to check the key and both models.

**About your key:** it is sent only from your browser straight to the provider you picked; there is no server in between. It is kept only for the current visit unless you tick **Remember the key on this device**, which stores it in this browser's local storage. Use a key with a spending limit, and don't tick Remember on a shared computer.

### 3. No key

Pick **No key: sample deck** to try the swiping with a built-in Vienna weekend deck.

## Cost

One 20-card session makes roughly 4 to 6 small card requests plus one longer write-up. With the default models that typically costs a few cents.

## Develop

Edit `index.html` and reload. Everything is in that one file: styles, markup and the script. The AI layer is the `aiText` / `aiJson` pair near the top of the script; add another provider there.

## Brand

The logo is three ruled index cards turning around one point: a brainstorm drawn as a storm of cards. Files in [`brand/`](brand/): `mark.svg` (the mark on its own) and `icon.svg` (app icon). The site uses `favicon.svg` and `apple-touch-icon.png`.
