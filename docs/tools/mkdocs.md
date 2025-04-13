---
title: MkDocs
---

MkDocs is a static site generator that's specifically designed for creating project documentation. It is simple to use, highly customizable, and supports Markdown for writing content. So this seemed the perfect fit writing documentation for my homelab project. This is what's being used to generate the documentation for this website.

If you look at the top right corner of the page, you can find a reference to the GitHub repository where the documentation is hosted.

## Theme
I'm using the [mkdocs-material](https://squidfunk.github.io/mkdocs-material/) theme, which is a popular and feature-rich theme for MkDocs. It provides a clean and modern look, along with many customization options.

## Previewing Documentation locally
To preview the documentation locally, the following Docker command is used:

```bash
docker run --rm -it -p 8000:8000 -v ${PWD}:/docs --entrypoint sh squidfunk/mkdocs-material \
  -c "pip install mkdocs-publisher && mkdocs serve -a 0.0.0.0:8000"
```

This command runs the MkDocs Material Docker image and serves the documentation on `http://localhost:8000`.

