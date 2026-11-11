# OpenChamber Docker builder

This repository publishes an amd64 Docker image built from the **official upstream OpenChamber release tag and Dockerfile**, using GitHub Actions and GitHub Container Registry (GHCR).

- Scheduled check: daily at 04:21 UTC.
- Manual: Actions → Build OpenChamber image → Run workflow.
- The workflow skips building a release if a matching image tag already exists in GHCR.
- Image: `ghcr.io/<github-username>/openchamber:latest` and `:<release-tag>`.
- OpenCode is installed at the version pinned by the official upstream Dockerfile. It is **not** independently updated by this workflow.
- The package may be private by default. Make it **Public** in GHCR package settings if you want Arcane to pull it without credentials.
- Deployment is intentionally **manual**. Switch the Arcane project's image from `edoor/openchamber:latest` to the GHCR image after verifying a successful build; preserve all existing volumes, environment variables, networks and ports.
- GitHub contains no company source code or API keys in this builder repository.

Upstream: https://github.com/openchamber/openchamber
