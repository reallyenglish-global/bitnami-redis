# Bitnami Redis container

This subdirectory contains the Bitnami Redis 8.10.3 Debian 12 container build context, extracted from [`reallyenglish-global/containers`](https://github.com/reallyenglish-global/containers/tree/main/bitnami/redis/8.10/debian-12) at source commit `2c19a2ed4cfb6f2a23ac69ec74ee09d68dbfcc25`.

The Dockerfile and supporting build files are licensed under Apache-2.0; see the repository-level [`LICENSE.md`](../LICENSE.md) and upstream notices. Redis is built from Bitnami's versioned downloads and checksum-verified during the image build.

## Build locally

From this directory, build and load the native-platform image locally:

```sh
docker buildx build --tag ghcr.io/reallyenglish-global/bitnami-redis:8.10.3-debian-12-r1 --load .
```

## GitHub Actions / image

Pull requests build both supported architectures without publishing. Pushes to `main` and manual runs on the default branch build and publish to GitHub Container Registry using the repository-scoped `GITHUB_TOKEN` (no external registry secret required).

Image references:

```text
ghcr.io/reallyenglish-global/bitnami-redis:8.10.3-debian-12-r1
ghcr.io/reallyenglish-global/bitnami-redis:latest
ghcr.io/reallyenglish-global/bitnami-redis:sha-<short-commit-sha>
```

The version tag records the Bitnami app, Debian, and image-revision versions. Tags can be changed in the registry; use an image digest when you need an immutable reference. `latest` is emitted only from the default branch.
