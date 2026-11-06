# tpix-blockscout-build

Unmodified builds of [Blockscout](https://github.com/blockscout/blockscout) backend and
[frontend](https://github.com/blockscout/frontend) release tags, used by the TPIX Chain explorer.

Upstream publishes public images only up to backend 9.0.2 and frontend v2.3.5. This repo builds
later tags on GitHub-hosted runners and attaches each image to a GitHub release as a gzip'd
`docker save` tarball with its SHA-256 sum.

## Build

Edit `versions.env` and push to `main`, or run the `build-images` workflow by hand.

## Load on a host

```bash
f=blockscout-12.0.4.tar.gz
curl -fLO https://github.com/xjanova/tpix-blockscout-build/releases/download/images-2026-11-07/$f
curl -fLO https://github.com/xjanova/tpix-blockscout-build/releases/download/images-2026-11-07/$f.sha256
sha256sum -c $f.sha256 && gunzip -c $f | docker load
```

Blockscout is licensed GPL-3.0; these images contain its unmodified source at the named tags.

Developed by Xman Studio
