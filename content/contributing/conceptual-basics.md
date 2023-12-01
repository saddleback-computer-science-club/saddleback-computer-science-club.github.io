---
title: 'Conceptual Basics'
date: 2023-11-28T10:09:05-08:00
draft: false

author: 'Matthew Reese'
summary: 'Covers Markdown, Hugo, and Git fundamentals.'

weight: 1
---

This page covers [Hugo](#Hugo), [Git](#Git), and [Markdown](#Markdown) fundamentals necessary zto understand for contributing to the site.

## Markdown
Markdown is a type of markup language, like HTML. Markup languages are used to specify how content should appear when rendered. For example, markdown allows you to create bold text by using two asterisks as follows: `**emboldened**`.

The syntax of markdown is extremely simple, almost like writing content in Microsoft Word or Google Docs.

## Hugo
Hugo is a highly configurable static site generator. A static site generator is, at its most basic, a program which converts some type of markup language into content renderable by your web browser. In Hugo's case, this means converting markdown into html.

Hugo makes heavy use of templates, allowing content to be made in a reusable and ultra-configurable way. Pages are written through markdown, parsed by hugo using any user-defined templates, and finally rendered as HTML.

## Git
Git is a widely used version control system \(often abbreviated VCS\). It is most often used for the management of a codebase. Git is an inherently collaborative system, allowing for contributions from numerous users.

**Repositories** are the file system that git will manage the history of. In our case, the repository is a single parent directory in which all site contents and configuration are stored.

A **commit** is, in simplified terms, a saved point in the history of your repository. It may help to imagine this like a *save point* in a video game; this *save point* being recoverable and stored indefinitely.

Deep-diving further into git would reveal it to be an extremely complex system with many subtleties. However, for the purposes of this site, usages of Git will be limited to only the most basic commands.

## Further Resources
- [Markdown Reference](/reference/markdown)
- [Hugo Documentation](https://gohugo.io/documentation/)
- [Git Book](https://git-scm.com/book/en/v2)