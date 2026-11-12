# Bitnami Redis Sentinel

Build context for the Bitnami Redis Sentinel `8.10.3` Debian 12 image. It runs the Sentinel daemon on port `26379` and is intended to monitor a separate Redis server; it is not a Redis data-server image.

## Image tag

```text
ghcr.io/reallyenglish-global/bitnami-sentinel:8.10.3-debian-12-r1
```

The tag follows the Bitnami release format: application version `8.10.3`, Debian `12`, image revision `r1`. The upstream Sentinel archive is checksum-verified for both amd64 and arm64 during the build.

## Build locally

From this directory, build the native-platform image and load it locally:

```sh
docker buildx build --tag ghcr.io/reallyenglish-global/bitnami-sentinel:8.10.3-debian-12-r1 --load .
```

This does not publish to GHCR. The repository workflow builds both `linux/amd64` and `linux/arm64`; publishing is limited to the default branch.

## Basic configuration

Set `REDIS_MASTER_HOST` to the Redis server Sentinel should monitor. Common related variables include `REDIS_MASTER_PORT_NUMBER` (default `6379`), `REDIS_MASTER_SET` (default `mymaster`), `REDIS_SENTINEL_QUORUM` (default `2`), and `REDIS_SENTINEL_PASSWORD`. Empty passwords are disabled by default; `ALLOW_EMPTY_PASSWORD=yes` is for development only. See the [upstream Redis Sentinel documentation](https://github.com/reallyenglish-global/containers/blob/2c19a2ed4cfb6f2a23ac69ec74ee09d68dbfcc25/bitnami/redis-sentinel/README.md) for the full configuration reference.

Source commit, release, and local modifications are recorded in [`UPSTREAM.md`](UPSTREAM.md). The repository-level Apache-2.0 license and upstream notices are retained.
