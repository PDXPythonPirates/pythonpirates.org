# Portland Python Pirates Website

This is the home for the content files used to create the [PDX Python Pirates][pythonpirates] website.

The content is written in [Markdown][markdown] and rendered to static HTML using [Hugo][hugo_site], a static site generation tool.

## How to Contribute: Overview

  1. [Fork][github_fork] this [repo][website_repo] to your GitHub account.
  1. [Clone][github_clone] to your local system and make content changes (see note on `git submodules` below)
  1. Run [Hugo][hugo_site] on your local system to verify your changes.
  1. Commit changes to your fork and open a [pull request][github_pr].

> Please note this repository make use of [git submodules][git_submodules] which requires an extra flag `--recurse-submodules` to fetch when cloning.

    git clone --recurse-submodules git@github.com:GITHUB_USER/pythonpirates.org.git

If you missed the submodules in the initial clone you can update using the following:

    git submodule update --init --recurse


## Verify Changes Locally

When making edits it is recommended you run a local installation of Hugo to verify the pages render as expected.

Fortunately, Hugo is not difficult to install and run.

See the official Hugo docs to:

* [Install Hugo][hugo_install] for your operating system.
* [Verify the executable][hugo_install_verify] is found in your PATH.

Once installed, start `hugo` from a command prompt with the project root as the current directory.

    # repo was cloned to directory 'pythonpirates.org'
    cd /path/to/git-projects/pythonpirates.org

    hugo server -D

This starts up a Hugo server listening on http://localhost:1313/

> The `-D` flag is optional and tells Hugo to include pages marked as "draft" status.

Make your edits & when finished:

* commit your changes locally... you made a branch, right? ;-)
* push to your fork on GitHub
* open a [pull request][github_pr]  
  _A preview of the site will be linked from the pull request ticket_
* notify someone in Slack to review the change and merge the pull request

## A Note on Front Matter and Drafts

Each content page starts with a section called _[front matter][front_matter]_.  This is easily identified at the top of the file within a section fenced by `---` or `+++`.

The front matter serves as a place to record metadata for the page such as author, background image, keyword tags, and more.  Most fields are self explanatory.

Front matter is also the place where a page is marked as a _draft_.  This is notable because Hugo does not publish pages marked as *draft* to our website.

You can override this behavior in your local installation by running `hugo` with the `-D` flag.  This is useful when authoring content that is not quite ready to be published but you want to check the rendered result.

Example front matter:

```
---
# comments starting with '#' are allowed in front matter
title: "Use Python to Take Over the World"
date:  2018-11-22
# page is marked as a draft and will not publish to the live site
draft: true
---
```

When you are ready to publish the page, update the value `draft: false`, or delete the `draft` attribute line.

> The `draft` attribute is the first thing to check if a page isn't showing up on the website that you expect.


[pythonpirates]: https://www.pythonpirates.org
[markdown]: https://guides.github.com/features/mastering-markdown/
[git_submodules]: https://blog.github.com/2016-02-01-working-with-submodules/#joining-a-project-using-submodules
[hugo_site]: https://gohugo.io/
[hugo_install]: https://gohugo.io/getting-started/installing/
[hugo_install_verify]: https://gohugo.io/getting-started/installing/#verify-the-executable
[front_matter]: https://gohugo.io/content-management/front-matter/
[contribute_overview]: https://www.pythonpirates.org/post/contribute-to-website/
[website_repo]: https://github.com/PDXPythonPirates/pythonpirates.org
[markdown]: https://guides.github.com/features/mastering-markdown/
[github_help]: https://help.github.com/
[github_fork]: https://help.github.com/articles/working-with-forks/
[github_clone]: https://help.github.com/articles/cloning-a-repository/
[github_pr]: https://help.github.com/articles/about-pull-requests/


