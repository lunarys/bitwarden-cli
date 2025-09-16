# bitwarden-cli

bitwarden-cli docker image

## Fork Note

This is a fork of the original repository. I've made the following adjustments:
- Added `wget` installation to the Dockerfile due to it being removed from the upstream container image
- Updated the workflow to build and publish images to my own container registry

For the original version, see the upstream repository.

## Overview

This is based on the code in the [external-secrets documentation](https://external-secrets.io/latest/examples/bitwarden/).

both the `Dockerfile` and `entrypoint.sh` are a near-identical copy/paste.

the only changes are to the `Dockerfile` to add shasum checking (thanks [majabojarska](https://github.com/majabojarska)!), and to convert `BW_CLI_VERSION` from an `ENV` to an `ARG`,
so that the official upstream version can be read from the `VERISON` file for the `ARG` as well as the image tag

# tag convention

```bash
docker pull ghcr.io/lunarys/bitwarden-cli:<official bitwarden cli version>
```

check [VERSION](/VERSION) to see what the actual value is.
when this doc was created it was `2023.12.1` so the full image was:

```bash
ghcr.io/lunarys/bitwarden-cli:2023.12.1
```
