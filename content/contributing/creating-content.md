---
title: 'Creating Content'
date: 2023-11-28T10:09:30-08:00
draft: false

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

All source in the site's content files comes in one of three forms: front matter, markdown, and shortcodes. Front matter contains metadata on the page itself (e.g. `author`, `title`). The markdown is what's actually rendered on the site. Finally, shortcodes are templates that allow for more complex content such as embedded videos.

### Front Matter

When you first open the newly created markdown file, it will probably have a header that looks something like this

```yml
---
title: 'Page Name'
date: 2023-12-01T00:00:00-8:00
draft: true

author: 'Unnamed'
---
```

The title field is exactly what you think it would be. By default, it's automatically set based on the filename, so you may need to change it.

Date is a date **and time** field, usually specifying when the article was created. Leave this as it is unless you are creating an event page, in which case it should be set to the date and time that the event will take place. [Unix time](https://unixtime.org/) is a great tool to easily create timestamps in this format; you'll want to use RFC3339 as that's the specification that hugo uses.

Draft is simply a field conveys to hugo that the page is unfinished; its main use in this site is to show authors whether pages are finished or not. This should be set to `false` once you're done writing.

Author should be set to your name, or to a list of names if there are multiple contributors. The syntax for this is `['My Name', 'Your Name', ...]`.

There are many more fields that may be useful to add, a list of which can be found in [hugo's docs](https://gohugo.io/content-management/front-matter/).

### Markdown

Here's a link to a [simple markdown syntax guide]({{< ref "reference/markdown" >}}), which is all that's really needed to begin writing content.

One small note: level 1 headers (i.e. `# Header`) should not be used as there should only be one per page, and the theme in use creates one for the title by default.

### Shortcodes

Hugo shortcodes are a way to display more complex content than is possible with markdown. You can find information about them, again, in [hugo's documentation](https://gohugo.io/content-management/shortcodes/). Here are a couple examples of how they may be used.

#### Embed a YouTube Video

```go-html-template
{{</* youtube dQw4w9WgXcQ */>}}
```

#### Display Code From Remote

```go-html-template
{{</* remoteCode "https://raw.githubusercontent.com/gcc-mirror/gcc/master/include/floatformat.h" */>}}
```

## Afterwards

Each time you finish contributing to a particular piece of content, it's a good idea to commit those changes and then run `git push`. That way, the same work is never done twice by team members, and the remote repository is always up to date with the latest changes.
