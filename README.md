# AI4S2 Website

Static homepage for the Center for AI for Social Science.

## Image Assets

Selected homepage images and faculty photos are stored under `assets/img/` and `assets/media/ppt/`.

## Blog Structure

Blog entries are plain static pages under `blog/<year>/<slug>/index.html`. The listing page at `blog/index.html` links to each entry, while the homepage `#blog` section highlights selected posts.

## GitHub Pages URLs

This site uses only relative asset paths, so the same code can be hosted at both:

- `https://ai4s2.github.io/`
- `https://freedomintelligence.github.io/ai4s2.github.io/`

## Bidirectional Sync

The two public repositories are kept aligned by `.github/workflows/sync-peer.yml`:

- `ai4s2/ai4s2.github.io`
- `FreedomIntelligence/ai4s2.github.io`

The sync workflow runs on a schedule and can also be triggered manually from GitHub Actions. It compares content hashes against `.github/sync-state.json`.

- If only one repository changed, the other repository pulls those changes.
- If both repositories changed since the last shared state, the workflow stops and reports a conflict instead of overwriting either side.
- Workflow files are intentionally excluded from automatic copy operations so GitHub Actions does not try to rewrite its own workflow definitions. If a workflow file changes, push that workflow update to both repositories manually.

For GitHub Pages, both repositories deploy with GitHub Actions from the repository root.

## Local Preview

Open `index.html` directly, or run:

```powershell
python -m http.server 8000
```

Then visit `http://localhost:8000/`.
