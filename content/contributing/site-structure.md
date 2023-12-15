---
title: 'Site Structure'
date: 2023-11-28T10:06:03-08:00
draft: false

author: 'Matthew Reese'
summary: 'Simplified file structure of the website.'

weight: 2
---

This page is broken up into two distinct sections, [writing](#writing) and [configuration](#configuration). If your intent is solely to publish content on this site, you need only to read the first section. The configuration section is meant for those with a bit of web development experience (or anyone willing to put some time into learning!) in modifying general aspects of the site, or to even help streamline content creation workflows.

## Writing

When creating website content, the only directory that you will ever need to worry about is—you guessed it—`/content`. Encapsulated within this, however, is the `_index.md` page along with numerous subdirectories whose purpose you should understand. Currently, they are as follows:

```
content/
├── contributing/
├── events/
├── projects/
├── reference/
└── _index.md
```

### `contibuting`

Contains the content for the contributing guide, what you are reading right now!

### `events`

Past and future events, and all associated assets. Currently, this is sorely underdeveloped.

### `projects`

Any medium - large scale scale projects whose content and explanations will benefit members of the club.

### `reference`

Generalized reference on computer science or cs adjacent content created on an as-needed basis.

### `_index.md`

Site homepage. Contains a list of all **future** events and links to all top-level content by default.

## Configuration

{{< todo >}}
