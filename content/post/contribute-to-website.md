---
title: "Contribute to this Website"
date: 2018-11-19
header_image: "/img/keyboard-closeup.jpg"
description: "Contribututions to our website are welcome and encouraged from community members!  This page describes how to get started."
images:
- "/img/ogp-preview-keyboard-500.jpg"
include_toc: true
tags: ["website", "hugo"]
---

# Overview: How to Contribute

  1. Fork the [GitHub repo][website_repo] that houses the content for the website.  
     You will need an account on GitHub to do this.
  1. Make edits to your own fork, preferably on a _branch other than_ `master`.
  1. Optionally, run a local copy of [Hugo][hugo_site] to verify the site renders as expected.
  1. Open a [Pull Request][pull_request] against the original repo.
  1. The website will automatically publish once the PR is merged.

# Static Site Generation

This website is built using a [static site generator][static_generator] that creates HTML pages by combining markdown content with HTML templates.

* This site uses [Hugo][hugo_site] for the site generator.
* All the source asset files (markdown content, HTML templates, images) are in a [repository on GitHub][website_repo].

Page content is written in [Markdown][markdown], a simplified way to format text that is easier to use than HTML.  Markdown file names typically end with an extension of `.md`.

Hugo looks for content pages under the `content` directory of the project root.  Most new page additions should be placed under `content/post`.

> For an example of markdown content see what is used to render [this very page][this_page].

## Run Hugo Locally

Instructions for getting started with Hugo can be found in the `README.md` of the root of the [website repo][website_repo].

## Open a Pull Request

GitHub has [comprehensive documentation][github_help] on using Git and GitHub tools.

See [here][pull_request] for details on opening a pull request.

If you have further questions, please don't hesitate to ask in our Slack group.


[hugo_site]: https://gohugo.io/
[website_repo]: https://github.com/PDXPythonPirates/pythonpirates.org
[static_generator]: https://www.staticgen.com/
[markdown]: https://guides.github.com/features/mastering-markdown/
[github_help]: https://help.github.com/
[pull_request]: https://help.github.com/articles/creating-a-pull-request/
[this_page]: https://raw.githubusercontent.com/PDXPythonPirates/pythonpirates.org/master/content/post/contribute-to-website.md
