# docker-python-black

> Source for the [fmariluis/black][] multiarch Docker image

(Repo forked from https://github.com/mccutchen/docker-python-black)

A minimal multiarch Docker image for running Python's [black] code formatter, useful in
CI pipelines or other situations where avoiding local Python/virtualenv/etc
installation is ideal.


## Automated builds

A new image is published automatically for every new release of black. See the
[bin/update][] script and the [Track upstream releases][workflow] workflow for
implementation details.

## Usage

An example CI step that will exit non-zero if any source code under the current
directory needs to be formatted:

```bash
docker run --rm -v $(pwd):/src fmariluis/black --check --diff /src
```

## Prior Art

There are at least a handful of existing, public docker images that serve the
same purpose as this one, but I wanted an image that a) explicitly tracked
black releases and b) published its Dockerfile.

Here are some other public images to consider:

- [kiwicom/black][] (lots of downloads, tracks black releases, but no public dockerfile)
- [cytopia/black][] (many downloads, public dockerfile, but does not track black releases)
- [houzefaabba/python3-black][] (fewer downloads, public dockerfile, tracks black releases, but outdated)

[black]: https://github.com/psf/black
[mccutchen/python-black]: https://hub.docker.com/r/mccutchen/python-black
[kiwicom/black]: https://hub.docker.com/r/kiwicom/black
[cytopia/black]: https://hub.docker.com/r/cytopia/black
[houzefaabba/python3-black]: https://hub.docker.com/r/houzefaabba/python3-black
[bin/update]: ./bin/update
[workflow]: ./.github/workflows/track_upstream_releases.yaml
