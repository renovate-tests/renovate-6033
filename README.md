Reproduction of https://github.com/renovatebot/renovate/issues/6033

This repository contains a `.gitlab-ci.yml` with 2 job definitions.
Both jobs refer to the same build image.

It is expected that renovatebot pins both image references when `pinDigest` is enabled.

Actually renovate fails to pin the second reference. In subsequent runs, renovate appends the docker digest again to the first reference making the image reference invalid.
