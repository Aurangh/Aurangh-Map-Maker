# Auranghzeb's Map Maker — Grid Combat Tracker

A single-file battle-map + initiative tracker for D&D 3.5 play-by-post games: paint terrain,
drop tokens, run initiative, export PNG/log straight into a forum or Discord post. Everything is
one `index.html` — open it in any modern browser.

Full feature guide: [`tracker-docs.md`](tracker-docs.md).

## Persistence

- **Local (automatic):** every change autosaves to the browser's IndexedDB. Survives reloads, but
  is tied to that one browser/device.
- **GitHub (durable, shareable):** the GM can sync maps to this repo as JSON commits. Each game is
  a folder under `saves/`; git history gives you free time-travel. **Players need no token** — they
  open a link and read the public JSON.

### GM (writes)
1. Open the app, click **☁ GitHub**.
2. Owner/repo/branch are auto-detected from the hosting URL; paste a **fine-grained Personal Access
   Token** (Contents: read & write on this repo). It's stored only in your browser.
3. **Push current map** to commit it (or tick *auto-push* to sync after edits). Browse/load synced
   maps from **🌐 Games**.

### Players (read-only)
Open a shared link — the app loads that map and drops into player mode automatically:

```
https://<owner>.github.io/<repo>/?game=<game-slug>&map=<map-slug>
```

Or open **🌐 Games** to pick from the list.

## Run your own copy

See [`SELF-HOSTING.md`](SELF-HOSTING.md) — fork the repo, enable Pages, make a token, done.
