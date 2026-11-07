# Cloudflare Pages — Safe Deployment Policy

**Checked:** 2026-11-07  
**Important:** This document records the safe target configuration. The Cloudflare account dashboard was not accessible through the connected GitHub tools, so no Pages project setting has been changed here.

## Required policy for each current class Pages project

- Production branch: `main`.
- Production deploy output: only the actual website output (the folder containing the intended `index.html`, viewer assets and site files).
- Preview deployments: disable them (`None`) during cleanup, or explicitly allow only a designated preview branch after review.
- Build watch paths: changes to documentation-only folders should not trigger a website build where supported.
- Audit files, raw API snapshots, CSV manifests and workflow notes must not become public website assets unless the application explicitly needs them.

## Important difference

**Build watch paths control whether a change starts a deployment. They do not remove files from an output folder.** To keep documentation out of the published site, configure the Pages build output directory so it contains only the site output, or keep non-site documentation outside that directory.

## Do not change these blindly

Do not set an output directory to `dist`, `public` or another guessed name. First inspect each repository's `index.html`, `viewer.html`, scripts, JSON paths, and any build scripts. Several of the current repositories serve page PDFs directly from their repository folder structure; moving those folders or changing the output root could break the viewer.

## Cloudflare dashboard review checklist

For each Pages project:
1. Open Settings → Builds & deployments.
2. Confirm the connected GitHub repository and production branch.
3. Record build command, root directory and build output directory before changing them.
4. Inspect Preview deployments and restrict/disable audit/feature branch previews during consolidation.
5. Inspect Build watch paths; exclude documentation-only paths if the project supports it.
6. Verify the latest production deployment and test the live viewer after any change.

Official Cloudflare documentation:
- Git integration and production/preview branch behavior: https://developers.cloudflare.com/pages/configuration/git-integration/
- Build watch paths: https://developers.cloudflare.com/pages/configuration/build-watch-paths/
- Build configuration: https://developers.cloudflare.com/pages/configuration/build-configuration/

## Current restriction

The Cloudflare dashboard could not be inspected or modified from this workspace. Therefore existing Page projects remain unchanged until their settings are checked directly. Do not treat a GitHub branch cleanup as proof that Cloudflare deployment settings are safe.


## Live GitHub workflow inspection — 2026-11-07

The following current-main workflow directories were checked across `tn-class-01` through `tn-class-12`:

- Classes 1–8 and 11: no `.github/workflows/` directory found on `main`.
- Class 9: `scert-c9-refresh.yml` runs manually or on pushes to `scert/refresh/class-09`; it checks out the triggering branch and pushes back to that same branch.
- Class 10: `scert-c10-refresh.yml` is scoped to `scert/refresh/class-10`; `scert-edition-sync.yml` is manual-only and defaults to `feature/scert-edition-pilot`, staging only the selected subject's `editions/` folder and `editions.json`; `scert-preview-page2.yml` uploads a temporary GitHub Actions artifact and does not commit files.
- Class 11: the official edition update workflow is manual-only and pushes the batch results to the triggering update branch.
- Class 12: `scert-c12-refresh.yml` is scoped to `scert/refresh/class-12`; the official edition update workflow is scoped to `scert/class-12/official-version-updates` and pushes only to that branch.

**Finding:** The inspected workflows do not directly call Cloudflare deployment APIs or push their results to `main`. They are GitHub content-ingestion / verification workflows scoped to non-production branches. However, a Cloudflare Pages Git integration can still create Preview deployments for non-production branch pushes if Preview deployments are enabled in the dashboard.

## What this means for document publishing

- Workflow staging lists do not prove that documentation is excluded from Cloudflare Pages.
- If a Pages project publishes the repository root as its output directory, `docs/`, CSV manifests and audit artifacts may be served as static files. This cannot be confirmed from GitHub alone.
- Build watch paths can stop documentation changes from triggering builds; they do **not** filter files out of the published output.
- Do not move PDFs or viewer assets into a guessed `public/` or `dist/` directory. Current viewers use repository-relative paths, so changing the root without a full URL/path audit can break books.
- The safe final design is to keep the Pages production branch on `main`, restrict or disable previews for working/audit branches, and publish a deliberate allow-listed site output while preserving the viewer's required book-page assets. This must be validated per repository in the Cloudflare dashboard before implementation.

**Still unverified:** Production branch, build command, root directory, output directory, Preview deployment policy and Build watch paths for each Cloudflare Pages project. No Cloudflare setting was changed.
