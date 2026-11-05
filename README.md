# CozyVTT – Docker Images

[![Build and Publish](https://github.com/Tsukoyachi/custom-cozy-vtt-packaging/actions/workflows/docker-build.yml/badge.svg)](https://github.com/Tsukoyachi/custom-cozy-vtt-packaging/actions/workflows/docker-build.yml)
[![GHCR](https://img.shields.io/badge/GHCR-Published-blue?logo=docker)](https://github.com/Tsukoyachi?tab=packages)

This repository contains GitHub Actions workflows to rebuild and publish the official [CozyVTT](https://github.com/CheekyChinchilla/CozyVTT) Docker images to GitHub Container Registry (GHCR).

The goal is to provide convenient, pre-built images for personal homelab deployments without having to build them locally.

## Published Images

| Component | Image |
|---|---|
| Backend | `ghcr.io/tsukoyachi/cozy-vtt-backend` |
| Frontend | `ghcr.io/tsukoyachi/cozy-vtt-frontend` |

### Available Tags

Each build publishes two tags per image:

- `latest` – Latest manually built version.
- `sha-<commit>` – Image associated with the exact upstream CozyVTT commit used for the build.

For example:

```bash
docker pull ghcr.io/tsukoyachi/cozy-vtt-backend:latest
docker pull ghcr.io/tsukoyachi/cozy-vtt-frontend:latest
```

To use a specific build:

```bash
docker pull ghcr.io/tsukoyachi/cozy-vtt-backend:sha-<commit>
docker pull ghcr.io/tsukoyachi/cozy-vtt-frontend:sha-<commit>
```

## Building Images

Images are built manually using GitHub Actions.

1. Navigate to the **Actions** tab.
2. Select **Build and Publish CozyVTT Images**.
3. Click **Run workflow**.
4. Enter the desired CozyVTT branch, tag or commit in `source_ref`.
5. Start the workflow.

The workflow will:

- Check out this repository.
- Check out the selected CozyVTT revision.
- Build the backend and frontend Docker images.
- Publish both images to GHCR.

No local Docker build environment or additional registry credentials are required.

## Upstream Project

These images are built from the original CozyVTT project:

- **Project:** [CheekyChinchilla/CozyVTT](https://github.com/CheekyChinchilla/CozyVTT)
- **Source code:** Maintained by the upstream project.
- **Dockerfiles:** Taken directly from the upstream repository.

This repository does not modify or maintain a separate copy of the CozyVTT application source code.

## License

CozyVTT is distributed under the [GNU Affero General Public License v3.0 (AGPL-3.0)](https://www.gnu.org/licenses/agpl-3.0.html).

Please refer to the upstream repository for the original license, copyright notices and applicable redistribution terms.

## Disclaimer

This is an independent community packaging project intended primarily for personal homelab use.

It is not affiliated with, maintained by, or officially endorsed by the CozyVTT upstream project.