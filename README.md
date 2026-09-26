# RobotUse anonymous demo page

Static project page for double-blind review. `index.html` at repo root, images under `assets/`. No build step, no external network calls.

## Option A (recommended): GitHub Pages on a fresh anonymous account

Gives a clean `https://<anon-user>.github.io/<repo>/` URL, like a real project page.

1. Create a brand-new GitHub account in a separate/incognito browser session: new email, a username unrelated to the authors/lab, no bio/avatar. Never star, follow, or commit anything else from this account.
2. Create a new **public** repo under that account (repo name can match the paper; that's fine, reviewers need to find it).
3. Push this folder:
   ```bash
   git remote add origin https://github.com/<anon-user>/<repo>.git
   git branch -M main
   git push -u origin main
   ```
4. Repo **Settings → Pages** → Source: `Deploy from a branch` → Branch `main` / `(root)` → Save. The page goes live at `https://<anon-user>.github.io/<repo>/` in a few minutes.
5. `.nojekyll` is already included so GitHub Pages serves the files as-is (no Jekyll processing).

## Option B: anonymous.4open.science (source-browser, not a real webpage host)

This service anonymizes an *existing* GitHub repo's owner/org/repo name/file contents, but it is a code/file browser, not GitHub-Pages-style hosting:
- Opening `index.html` does render it inline (not just syntax-highlighted source), but inside their site's viewer frame (`anonymous.4open.science/r/<id>/index.html`), with the file tree and Source/Raw/Download buttons still showing — not a clean standalone page.
- JavaScript is off by default and sandboxed even when toggled on (external scripts errored with a DOMPurify sanitization failure in testing) — fine for this page since it's plain HTML/CSS/images with no JS.
- The sidebar always shows a **"Source commit \<date\>"** watermark, and updates to the original repo are live-reflected — so edits after your submission deadline are visible to anyone re-checking the link.

To use it: push to any public repo (identity doesn't matter as much since the service anonymizes owner/repo/filenames), then submit the repo URL at https://anonymous.4open.science/ and share the generated `anonymous.4open.science/r/...` link — never the raw `github.com/...` URL.

## Before pushing, double check

- `git log` on this repo shows author `Anonymous <anonymous@anonymous.com>` (set locally in this repo only) — confirm the remote account you push to also carries no identifying name/email/avatar.
- Strip any EXIF/identifying metadata from images if they were exported with author info embedded.
- The abstract's numbers (45.00% / 38.33% / 20.00%) are copied from the current paper draft, which is marked as a **prospective/unverified** abstract in `overleaf-project/sec/00_abstract.tex`. Re-check against final evaluation results before making this page public.
