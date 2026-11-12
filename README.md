# ReallyEnglish Bitnami Redis images

This repository maintains separate build contexts for the Redis family. Each component lives in its own directory so additional upstream containers can be added without sharing image files or startup scripts.

## Components

- [`bitnami-redis/`](bitnami-redis/README.md) — Redis server, version `8.10.3-debian-12-r1`.
- [`bitnami-sentinel/`](bitnami-sentinel/README.md) — Redis Sentinel, version `8.10.3-debian-12-r1`.

The GitHub Actions workflow builds both contexts for `linux/amd64` and `linux/arm64`. Pull requests and non-default-branch runs build without publishing. Pushes to `main` and manual runs on the default branch publish each image to GHCR with its version, commit-SHA, and `latest` tags. Keep the `version` entries in the workflow matrix aligned with each component's `VERSION` file and Dockerfile.

After the first successful publication, set each GHCR package's visibility to **Public** in GitHub package settings if unauthenticated public pulls are intended. Newly created packages may default to private; local builds do not publish or change package visibility.

## Local Redis build

From the repository root, build and load the native-architecture image into the local Docker engine:

```sh
docker buildx build --tag ghcr.io/reallyenglish-global/bitnami-redis:8.10.3-debian-12-r1 --load bitnami-redis/
```

This builds locally and does not publish the image.

## Local Sentinel build

From the repository root, build and load the native-architecture image into the local Docker engine:

```sh
docker buildx build --tag ghcr.io/reallyenglish-global/bitnami-sentinel:8.10.3-debian-12-r1 --load bitnami-sentinel/
```

This builds locally and does not publish the image. For both supported architectures, use the GitHub Actions build workflow.

## Licensing and provenance

The repository-level [`LICENSE.md`](LICENSE.md) and component-specific upstream notices apply. Sentinel source provenance and local changes are recorded in [`bitnami-sentinel/UPSTREAM.md`](bitnami-sentinel/UPSTREAM.md).
