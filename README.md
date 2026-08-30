# 🎮 just-one-more-run

A living game-library tracker **and** a taste-DNA recommendation engine — in a single, dependency-free HTML file.

Named after the only sentence a roguelite player has ever told themselves honestly.

It started as one player's catalog across **Steam, Nintendo Switch 2, and PlayStation 5**, but the recommender is built for anyone: plug in the systems you own and the vibes you're chasing, and it ranks games you don't already have by how well they match.

> **Status:** private repo for now. When you're ready to share it, flip it to public and turn on GitHub Pages (see *Going public* below) for a free live site.

---

## What's inside

- **Player dossier** — headline stats and a **Taste DNA** panel that weights your genres by real playtime.
- **The Library** — every owned game by platform, filterable by system and genre, with `Playing / Backlog / Done` toggles. Add your own titles too.
- **For You** — hand-matched picks you *don't* own, filtered to systems you own, sorted by match strength.
- **The Recommender** — the shareable heart of it: pick systems + vibes, get ranked matches. Others can run it for their own setup.
- Everything you toggle or add **saves to your browser** (`localStorage`) — no account, no backend.

## Design

- Single file, **zero build step, zero dependencies** (only Google Fonts over the network).
- **Light + dark themes** with a manual toggle, driven entirely by CSS custom properties.
- Genre-coded typographic cover tiles — no copyrighted box art, no image hosting.
- Arcade "player dossier" identity: Chakra Petch / Barlow / JetBrains Mono on a warm-violet ground.

## Run it locally

It's just a static file. Open `index.html` in any browser, or serve it:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Push it to GitHub (private)

From inside this folder:

**Easiest — with the [GitHub CLI](https://cli.github.com/):**

```bash
gh repo create just-one-more-run --private --source=. --remote=origin --push
```

**Or manually:** create an empty private repo named `just-one-more-run` on github.com (no README/license — this repo already has them), then:

```bash
git remote add origin https://github.com/griffized/just-one-more-run.git
git push -u origin main
```

## Going public later

Whenever you want to share it:

1. Repo **Settings → General → Danger Zone → Change visibility → Public**.
2. **Settings → Pages → Deploy from a branch → main → / (root) → Save**.
3. In ~1 minute it's live at `https://griffized.github.io/just-one-more-run/`.
4. Add that link back here at the top of the README.

_(GitHub Pages needs a public repo on the free plan, which is why there's no live site while this stays private.)_

## Make it your own

Open `index.html` and edit the data arrays near the bottom `<script>`:

- `LIB` — your owned games: `{ n:"Title", p:["pc","ps5","switch2","xbox"], g:"roguelite", h:120 }`
- `REC` — the recommendation pool (games not owned), each with `g:[genres]` and a `hook`.
- `DNA` — your genre weighting for the Taste DNA bars and the "For You" ranking.
- `GEN` — the genre taxonomy and each genre's accent color.

Platforms: `pc`, `ps5`, `switch2`, `xbox`. Genres are the keys of `GEN`.

## License

MIT — see [LICENSE](LICENSE). Do whatever you like with it.
