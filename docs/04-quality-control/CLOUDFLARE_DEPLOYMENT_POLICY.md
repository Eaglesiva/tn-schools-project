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
