---
title: "Making Draft Content Visible"
date: "2018-11-18"
lastmod: "2019-01-01"
author: ""
header_image: "/img/keyboard-closeup.jpg"
draft: true
pinned: true
---

# Example Unpublished Content

Under normal operation Hugo does not render pages marked as _draft_ in the front matter at the top of the markdown file:

```
---
title: ...
date:  ...
draft: true
---
```

When authoring a file locally it can be useful to verify content renders as expected before marking a post as no longer in "draft".

To do this, run Hugo server with the `-D` flag (for **D**rafts) and all pages, draft or not, will be processed.

```
hugo server -D
```
