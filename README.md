# Sméan Spin Wheel

Single-page static spin-to-win wheel. No build step — `index.html` plus `assets/` is the whole site.

## Run locally

```sh
python3 -m http.server 8000
```

Then open http://localhost:8000. Open the file directly with `file://` only for a quick look; a server matches how GitHub Pages serves it.

## Deploy

Pushing to `main` triggers `.github/workflows/deploy.yml`, which publishes the repository root to GitHub Pages. The workflow enables Pages itself, so there is no Settings toggle to flip — but Pages on a **private** repo requires GitHub Pro or higher.

`.nojekyll` only matters if the Pages source is ever switched to *deploy from a branch*; the Actions deploy above skips Jekyll entirely and strips root dotfiles from the artifact.

Asset paths are relative and lowercase, so the site works from a project subpath (`/<repo>/`) as well as a custom domain.
