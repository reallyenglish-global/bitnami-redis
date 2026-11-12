# Bitnami Redis container

This repository contains the Bitnami Redis 8.10.3 Debian 12 container build context, extracted from [`reallyenglish-global/containers`](https://github.com/reallyenglish-global/containers/tree/main/bitnami/redis/8.10/debian-12) at source commit `2c19a2ed4cfb6f2a23ac69ec74ee09d68dbfcc25`.

The Dockerfile and supporting build files are licensed under Apache-2.0; see [`LICENSE.md`](LICENSE.md) and the upstream notices. Redis is built from Bitnami's versioned downloads and checksum-verified during the image build.

## Build locally

```sh
docker buildx build --platform linux/amd64,linux/arm64 -t bitnami-redis:local .
```

## GitHub Actions / image

Pull requests build both supported architectures without publishing. Pushes to `main` and manual workflow runs build and publish to GitHub Container Registry using the repository-scoped `GITHUB_TOKEN` (no external registry secret required).

After the first successful publication, set the GHCR package visibility to **Public** in the package settings (or through the GitHub Packages API). Image reference:

```text
ghcr.io/reallyenglish-global/bitnami-redis:latest
ghcr.io/reallyenglish-global/bitnami-redis:sha-<short-commit-sha>
```

Tags are immutable commit identifiers plus `latest` on the default branch.
