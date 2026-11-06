# synthese-party-app

Placeholder "kommt bald" page for **https://party.synthese-dresden.de** — the future synthese party project.
A single static page (`public/index.html`) served by nginx; no build step, no dependencies.
Fonts are self-hosted (`public/fonts/`), the doodles are the synthese Elements inlined as SVG.

## Deploy with Coolify

1. Coolify → **Projects → Synthese → production → + New → Public/Private Repository**
   → this repo, branch `main`.
2. **Build Pack: Dockerfile** (the `Dockerfile` in the repo root).
3. **Domains:** `https://party.synthese-dresden.de` — **Port 80**.
4. **Deploy.** The DNS record `party` → the VPS IP already exists, so the
   HTTPS certificate is issued automatically.

## Change the text

Edit `public/index.html`, commit, push, redeploy (or enable the GitHub webhook in Coolify).

## Local preview

```bash
docker build -t synthese-party-app . && docker run --rm -p 8080:80 synthese-party-app
```

Then open http://localhost:8080
