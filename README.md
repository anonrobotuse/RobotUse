# RobotUse anonymous demo page

Static project page for double-blind review. `index.html` at repo root, images under `assets/`. No build step, no external network calls.

## Publish anonymously via anonymous.4open.science

1. Push this repo to a **public** GitHub repo whose owner/repo name does not reveal identity (e.g. an existing anonymous account, or a repo name unrelated to the authors/lab).
   ```bash
   git remote add origin <your-anonymous-repo-url>
   git branch -M main
   git push -u origin main
   ```
2. Go to https://anonymous.4open.science/ and submit the repo URL.
3. When generating the link, enable the **webpage** option so `index.html` is served (not just the code browser).
4. Use the generated `anonymous.4open.science/...` link in the paper/supplementary material — never link the raw `github.com/...` URL, since that defeats the anonymization.

## Before pushing, double check

- `git log` on this repo shows author `Anonymous <anonymous@anonymous.com>` (set locally in this repo only) — confirm the remote account you push to also carries no identifying name/email/avatar.
- Strip any EXIF/identifying metadata from images if they were exported with author info embedded.
- The abstract's numbers (45.00% / 38.33% / 20.00%) are copied from the current paper draft, which is marked as a **prospective/unverified** abstract in `overleaf-project/sec/00_abstract.tex`. Re-check against final evaluation results before making this page public.
