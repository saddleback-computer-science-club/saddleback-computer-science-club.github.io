---
title: 'Contributing Guide'
date: 2023-11-14T17:11:57-08:00
draft: false

author: 'Matthew Reese'

unlisted: true
---

## Info

The following pages have been created as resources to aid anyone who wishes to contribute to content to this website. I recommend going through these in the order that they appear, as some pages will build on those prior. If you have any further clarifying questions after reading these, or believe that some content on these pages is in need of correction, please contact me via Discord or email.

On this page is a basic overview of how to get yourself setup to work on the site.

If you want to delve further into any of the concepts below, each page contains a curated list of resources that may provide more information.

### Quick Start

1. Download and install [Git](https://git-scm.com/download), [Hugo](https://gohugo.io/installation/), and an editor such as [Visual Studio Code](https://github.com/gohugoio/hugo/releases/latest).

2. Clone the repository:

    ```console
    git clone --recurse-submodules \
        https://github.com/saddleback-computer-science-club/saddleback-computer-science-club.github.io.git \
        website
    ```

3. Create a new branch for your work using:

    ```console
    git checkout -b feature/<name>
    ```

    Where `<NAME>` is a descriptive name of the new page(s).

4. Run the following command to create a new markdown file from archetype:

    ```console
    hugo new content <location>
    ```

5. Update the page front matter
    - Set `author` to your name
    - Ensure `title` is correct
    - Change `draft` to `false` (once you're done of course)

6. Write! Add content to the file using [markdown syntax](http://localhost:1313/reference/markdown/) and [hugo shortcodes](https://gohugo.io/content-management/shortcodes/).

7. Push your changes to the remote repository by running

    ```console
    git push -u origin
    ```

8. Create a [pull request on github](https://github.com/saddleback-computer-science-club/saddleback-computer-science-club.github.io/compare) to mark your submitted changes as *ready for review*.