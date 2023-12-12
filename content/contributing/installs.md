---
title: 'Install Guide'
date: 2023-11-28T13:03:43-08:00
draft: false

author: 'Matthew Reese'
summary: 'Outline of necessary software for contributing to the website.'

weight: -1
---

Necessary software is as follows: [Hugo](#hugo), [Git](#git), [some kind of code editor](#editor). This guide is written for those using Windows. If you have questions about installing on a different operating system, read the documentation linked under each section. If you're still struggling after reading these pages and googling, feel free to contact me. If you already have any of these installed, you may freely skip that section of the page.

## Git

To install Git, go to their [official download page](https://git-scm.com/download/win) and click to download either the 32-bit or 64-bit installer, depending on your system. If in doubt and you have a relatively old machine, download the 32-bit version. 

When running the installer, you will be prompted with a series of options. Unless you understand what each of the prompts mean, I recommend just pressing next repeatably until you reach the end. Pretty much all of the defaults git provides are quite sensible.

For a more comprehensive install guide, and help with other operating systems, see [Git's documentation](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

## Hugo

A local installation of hugo is essential for looking at your rendered edits *before* submitting them to the main website. To install, find the edition for your operating system on [hugo's releases page](https://github.com/gohugoio/hugo/releases/latest). You will want to download the file **hugo_extended_X.XXX.X_OS-ARCH.zip** where *X.XXX.X* is the current version number, *OS* is your operating system and *ARCH* is your machine's architecture.

Once you have downloaded the compressed folder, follow [this section of hugo's guide](https://gohugo.io/installation/windows/#prebuilt-binaries) on installing with prebuilt binaries.

## Editor

In order to make write the markdown content for the site, you need some sort of text editor. Preferably this editor would be superior to Windows' notepad, with features like multi-file editing, syntax highlighting, and maybe even Git integration.

For the sake of brevity, I will be providing a small guide on installing the easy-to-setup editor Visual Studio Code (VSCode). Below are links to some other decent editors, if you wish to check those out instead.

- [Sublime Text](https://www.sublimetext.com/): Simple and minimalistic editor, but also extremely extensible. 
- [Pulsar](https://pulsar-edit.dev/): Fork of GitHub's *Atom* editor. Selling point is its excellent integration with Git.

To get started with VSCode, download the install executable from their [official site](https://code.visualstudio.com/download). That's it! Once the the file has finished installing, you're ready to open up VSCode and move on to the next section.
