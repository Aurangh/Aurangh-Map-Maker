# Self-hosting & running your own games

The app commits map saves to **its own repo** — it auto-detects `owner/repo` from the URL it's
served from. So running your own copy is just: fork → enable Pages → make a token.

## Run your own instance (fork)

1. **Fork** this repo into your GitHub account.
2. **Enable GitHub Pages:** repo **Settings → Pages → Build and deployment → Deploy from a branch →
   `main` / `/ (root)`**. After a minute your app is live at
   `https://<your-username>.github.io/<repo-name>/`.
   - The repo must be **public** so your players can read saves without logging in.
3. **Create a token:** GitHub **Settings → Developer settings → Fine-grained personal access tokens
   → Generate new token**. Scope it to **only your fork**, permission **Contents: Read and write**.
   Copy the `github_pat_…` string.
4. **Open your app**, click **☁ GitHub**. Owner/repo/branch should already be filled in from the
   URL — paste your token and **Save settings**.
5. **Push a map.** It commits to `saves/<game>/<map>.json` in your fork. Share the player link:
   `https://<you>.github.io/<repo>/?game=<game-slug>&map=<map-slug>`.

Your token lives only in your browser's `localStorage` — it is never committed and never shared.
Players never need one.

## Add a co-GM to your repo

If someone else should be able to **write** to *your* repo (shared game library):

1. Repo **Settings → Collaborators → Add people** → invite their GitHub account.
2. They accept, then generate **their own** fine-grained PAT (Contents: Read and write on your repo)
   and paste it into the app under **☁ GitHub**.

Everyone with write access shares the same `saves/` folders. It's last-write-wins — coordinate so
two GMs aren't editing the same map at the same second.

## Notes & limits

- **Public repo = public saves.** Anyone with the link can read your maps. Fine for play-by-post;
  don't put anything private in a map you sync.
- **Imported background images aren't synced** (kept local to keep commits small). Terrain, tokens,
  fog, initiative, and the log all sync.
- **Renaming** a map's title or campaign changes its file path (creates a new file); delete the old
  one from the repo if you don't want it lingering.
- The local IndexedDB autosave still works offline — GitHub is the durable layer on top.
