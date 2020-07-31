# docker-python-black

> Source for [mccutchen/python-black][] docker image

A minimal docker image for running Python's [black] code formatter, useful in
CI pipelines or other situations where avoiding local Python (and virtualenv,
etc) installation is ideal.

## Usage

An example CI step that will exit non-zero if any source code under the current
directory needs to be formatted:

```bash
docker run --rm -v $(pwd):/src mccutchen/python-black --check --diff /src
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
