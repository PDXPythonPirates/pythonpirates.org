Website Management
==================

This document provides a summary overview of how the [Python Pirates website][pirates] is built, deployed, and updated.

Information on how to develop the website using [Hugo][hugo] can be found in the [README.md][readme].


# Key Points

  * The content is static HTML built at deployment using a website generator
  * Website source is managed on [Github][this_repo] available for updates via Pull Request
  * The generated website is hosted on [Netlify][netlify]
  * The Github repo uses Netlify tooling to facilitate automatic builds and deployments
  * Netlify automatically manages the TLS certificates using [Let's encrypt][lets_encrypt] (yay `https`)
  * The DNS is manually managed with Namecheap.com


# Generated Static Content

The content for the site is produced using [Hugo][hugo], a [static site generator][static_gen].  This results in what it sounds like: _static files_ comprised of HTML, CSS, and javascript content.

Static content makes the site cheap to host (free) and also reduces the surface area of possible security attacks associated with a full fledged web application.

We use a site generator tool to reduce maintenance and overhead in managing static content files.  For example, a common UI component such as the header can be changed in one template file and applied to the entire site rather than hand editing dozens or more affected HTML files.

Authored content is written in [Markdown][markdown], a simplified mark up language.  Markdown tends to be easier to write and maintain than HTML due to less syntax clutter.


# Automatic Deployments

Changes to the main [Github repo][this_repo] trigger automatic updates to Netlify:

  * Pull Requests trigger the generation of a _preview deployment_ under a unique netlify URL.  
  This URL is presented as `deploy-preview` in the pull request details, available for visual inspection before merge.  
  [Example PR](https://github.com/PDXPythonPirates/pythonpirates.org/pull/126)  
  [Example deploy-preview](https://deploy-preview-126--pythonpirates.netlify.com/)
  * Any change to the GitHub `master` branch (e.g. merge a pull request) triggers live site deployment.  
  The site generation usually completes a few seconds after the git merge.  
  Live site deployment is handled automatically by Netlify.
  
Note: this triggered deployment process only applies to the main Github repository and not any forks outside our Github organization.

Netlify manages and automatically renews website TLS certificates using the free service [Let's Encrypt][lets_encrypt].  The one requirement is we control rights to the domain, which currently expire in December 2020.





[netlify]: https://www.netlify.com
[lets_encrypt]: https://letsencrypt.org
[pirates]: https://www.pythonpirates.org
[readme]: https://github.com/PDXPythonPirates/pythonpirates.org/blob/master/README.md
[this_repo]: https://github.com/PDXPythonPirates/pythonpirates.org/
[hugo]: https://gohugo.io
[static_gen]: https://www.staticgen.com/
[markdown]: https://guides.github.com/features/mastering-markdown/
