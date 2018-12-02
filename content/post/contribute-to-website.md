---
title: "Contribute to this Website"
date: 2018-11-19
author: "Matt Phillips"
author_twitter: "i_mattman"
author_github: "imattman"
header_image: "/img/keyboard-closeup.jpg"
tags: ["website", "hugo"]
# pinned: true
---

# How to Contribute to this Website

## The Nutshell Version

  1. Fork the [GitHub repo][website_repo] that houses the content for the website.  You will need an account on GitHub to do this.
  1. Make edits to your own fork, preferably on a branch other than `master`.
  1. Optionally, run a local copy of [Hugo][hugo_site] to verify the site renders as expected.
  1. Open a **[Pull Request][pull_request]** against the original repo.
  1. The website will automatically publish once the PR is merged.

## Additional Details

This website is generated using a static site generator that combines markdown content files with HTML templates to yield the final web pages.

* [Hugo][hugo_site] is the static site generator.
* The markdown content, templates, images, and other assets are in a [repo on GitHub][website_repo].

Page content is written in [Markdown][markdown], a simplified way to format text that is easier to use than HTML.  By convention, Markdown files end with the `.md` extension.

Hugo looks for content pages under the `content` directory of the project root.  Most new page additions should be placed under `content/post`.

> For an example of markdown content see what is used to render [this very page][this_page].

### Run Hugo Locally

Instructions for getting started with Hugo can be found in the `README.md` of the root of the [website repo][website_repo].

### Open a Pull Request

GitHub has [comprehensive documentation][github_help] on using Git and GitHub tools.

See [here][pull_request] for details on opening a pull request.

If you have further questions, please don't hesitate to ask in our Slack group.


[hugo_site]: https://gohugo.io/
[website_repo]: https://github.com/PDXPythonPirates/pdxpythonpirates.org
[markdown]: https://guides.github.com/features/mastering-markdown/
[github_help]: https://help.github.com/
[pull_request]: https://help.github.com/articles/about-pull-requests/
[this_page]: https://raw.githubusercontent.com/PDXPythonPirates/pdxpythonpirates.org/master/content/post/contribute-to-website.md
