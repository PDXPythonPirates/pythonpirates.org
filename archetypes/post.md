---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
author: "Your name"
description: "{{ replace .Name "-" " " | title }}"

# twitter and github are optional
#author_twitter: "twitter-handle"
#author_github: "github-name"

header_image: "/img/keyboard-closeup.jpg"
# preview image displayed in Slack link
#preview_image: "/img/..."

# include Table of Contents in side nav
include_toc: true
draft: true
---

