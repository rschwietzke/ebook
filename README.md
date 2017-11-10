# barebones-ebook

This is a starter repository for creating a technology ebook using asciidoctor.

If you're unfamiliar with asciidoctor, check out the [official reference](http://asciidoctor.org/docs/asciidoc-syntax-quick-reference/).

This repository is setup to provide a minimal structure for organizing your book. It also outputs to:

* HTML
* PDF
* Epub3
* Kindle (Epub)
* Mobi
* Docbook

These options are controllable via switches to the build script. For options, run:

```
build -h
```

# Make it yours

Clone this repository. Then, start over!

```
cd your_cloned_repository
rm -rf .git
git init
git add .
git commit -m 'Initial commit'
```

Now, edit `preview.adoc` and `book.adoc` with your name, version/copyright, and book title. 

Modify the example text under `./book`. You can use your favorite text editor. The excellent [Asciidoc FX](http://asciidocfx.com/) offers quick edit options which are especially helpful if you're not too familiar with asciidoc. It also has a preview panel so you can track changes as you type.

Have fun!

# Building

The simplest way to build this book's contents is via docker:

```
docker run \
    -v $PWD:/src \
    --workdir /src \
    --entrypoint /src/build asciidoctor/docker-asciidoctor:latest -pekdf book.adoc
```

This command uses the official asciidoctor docker image to build the book artifacts.

To install and run asciidoctor locally, follow the [official installation instructions](http://asciidoctor.org/docs/install-toolchain/).

# CI

This repository is setup to compile your book automatically via Gitlab's CI pipeline.

Book artifacts are cached for 1 week. See `.gitlab-ci.yml` for full details.

# License

This barebones project and any related asciidoctor examples are licensed under the MIT license.

The cheatsheet example was taken from [Dan Allen's Sample Gist](https://gist.github.com/mojavelinux/4402633).

See [LICENSE](./LICENSE) for full text.
