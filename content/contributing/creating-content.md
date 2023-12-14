---
title: 'Creating Content'
date: 2023-11-28T10:09:30-08:00
draft: true

author: 'Matthew Reese'
summary: 'Guide for writing website pages.'

weight: 3
---

Creating pages for this site involves running a command to create the markdown file, then simply editing the file. It is not necessary to understanding the intricacies of hugo, html, or anything going on at the lower level; knowing **what** the command does and the basics of markdown is more than enough to begin contributing.

## Getting the Files

First thing's first, you'll need a local copy of the site files before you can think about doing anything else. If you haven't already, make sure that all of the programs listed in [the install guide](./installs) have been installed.

Start off by finding a nice, memorable place in your system to work, then run the command below. Feel free to press the `copy` button found at the top-right of the code block so that you don't need to type it out manually.

```console
git clone --recurse-submodules \
    https://github.com/saddleback-computer-science-club/saddleback-computer-science-club.github.io.git \
    website
```

## Creating a Page

The following command will create a new page (markdown file from template) at `<location>`, **relative to the `content` directory**:

```console
hugo new content <location>
```

For example, to create a new reference page on python dictionaries I would run

```console
hugo new content reference/python/dictionaries.md
```

## Editing the File

Ok, so you've got a new file; now what? 