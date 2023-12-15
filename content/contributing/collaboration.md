---
title: 'Collaboration'
date: 2023-11-28T10:10:10-08:00
draft: false

author: 'Matthew Reese'
summary: 'How to collaborate on this  project in an organized way.'

weight: 3
---

## Abstract

As I have outlined in the previous few guides, GitHub and by extension, Git, will be used to organize collaboration on development.

This project will be organized under the [shared repository model](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/getting-started/about-collaborative-development-models#shared-repository-model). This basically means that each change involves creating a new branch, and later opening a pull-request to initiate team review.

If you've used Git before, you may be thinking: "Why not just go the simple route and commit all changes directly to `main`/`master`?" Well first of all, this approach is extremely dangerous when working with a team. Each and every commit goes directly into building the running site, with absolutely no review or testing process in between. This opens up opportunities for erroneous information, or even a broken site if developers aren't careful.

## How-To

The most important command that you will need to run often is `git pull`. This will update your local repository to ensure that you have the latest changes. I recommend running this **every time you sit down to work on content**.

This section covers the concrete steps you need to take in developing for two separate scenarios. See [Creating a New Topic Branch](#creating-a-new-topic-branch) if you're beginning development a new page (or set of pages). Otherwise, see [Working Together on Projects](#working-together-on-projects) for collaborating on projects that already have a branch created.

### Creating a New Topic Branch

To start a new project for a page or group of pages, run the following two commands:

```console
git checkout -b feature/<topic name>
git push -u origin feature/<topic name>
```

After that, you are free to make changes and commits, then run `git push` to update the remote repository.

For example, if I wanted to create a page on the breadth first search algorithm I would run something like the following:

```console
git checkout -b feature/bfs-algorithm
git push -u origin feature/bfs-algorithm
```

Then, once I've made some changes and committed them to my local repository and commit them, I can run `git push` to update the remote repository (on GitHub) accordingly.

### Working Together on Projects

To access a branch that other developers have been working on simply run

```console
git switch <topic name>
```

For example, to work on content for the guide you're reading right now, one would run:

```console
git switch feature/contributing-guide
```

## Committing Changes

Branches are great, but they're pretty useless if you don't know how to commit to them. The next page will cover how to make those changes in the context of Hugo; for now, just assume that you've modified a few files and created a page or two. Once you have made said changes on your local machine, you can run the command:

```console
git commit -am "<well-written message>"
```

This command will stage and commit all the changes you've made to your local copy with the message in quotes.

If you wish to be more particular about which files are committed you can use the `git add` command first. (A reason to do this may be that you're still working on one page, but have finished another and want to add it to the remote repository). The syntax for this is as follows:

```console
git add <file 1> [<file 2> ...]
git commit -m "<well-written message>"
```

Note the missing **-a** flag in this example. That is shorthand for running `git add .` (staging all changes) and then `git commit`, which is specifically what we want to avoid doing here.

## Synchronizing With Remote

As I emphasized in the [how to](#how-to) section, it's important to run `git pull` very often so that you stay in sync with the work other developers are doing.

Equally as important is to run `git push` so that other developers can see your changes and work together (if applicable).

## Submitting Changes for Review

Once you've finished work on the branch and believe that it's ready to exist on the website, submit a pull request on GitHub. Follow [this link](https://github.com/saddleback-computer-science-club/saddleback-computer-science-club.github.io/compare) to begin. Then, under the dropdown labelled *compare*, choose the branch that you have been working on. After that, click the *Create pull request* button, which should have turned bright green. You will be prompted with a text box to write a description in. Write as much or as little as you feel is necessary.

Once you follow those steps all you have left to do is wait. Reviewers will be notified of the new request and either accept it, fix errors, or possibly question you regarding the changes.

## Putting It All Together

To help you understand everything above, here's what an example workflow might look like for the creation of a hypothetical python dictionary guide. This will be done collaboratively between two developers, **Dev 1** and **Dev 2** over the course of a few days.

**Dev 1:**

1. ```console
    git checkout -b feature/python-dict-reference
    git push -u origin
    ```

2. *Create file `content/reference/python/dicts/_index.md`.*

3. *Add a short intro to new file, explaining dicts.*

4. ```console
    git commit -am "Created _index.md. Short explanation introducing dicts"
    git push
    ```

**Dev 2:**

1. ```console
    git pull
    git switch feature/python-dict-reference
    ```

2. *Create files `content/reference/python/comprehension.md` and `content/reference/python/dicts/iterating.md`.*

3. *Add relevant content to both files.*

4. ```console
    git add content/reference/python/dicts/comprehension.md
    git commit -m "Created dict comprehension reference"
    git add content/reference/python/dicts/iterating.md
    git commit -m "Created dict iteration reference"
    git push
    ```

**Dev 1:**

1. ```console
    git pull
    ```

    *(Aleady on branch `feature/python-dict-reference` from before)*

2. *Look at new files from **Dev 2**.*

3. *Fix mistakes in `iterating.md` file.*

4. ```console
    git commit -am "Fixed grammar errors in iterating.md"
    git push
    ```

**Dev 2:**

1. ```console
    git pull
    ```

    *Looks over files andd decides that everything is complete.*

2. *Creates pull request on GitHub to be reviewed.*

## Other Git Tips

- It's worth mentioning again and again, run `git pull` very often.

- Suppose you started making changes on your local main branch, forgetting  to create or switch to the new `feature` branch. You certainly don't want to lose those changes, so the simplest way to fix this is by running `git stash` then creating/switching to the branch by following the [how to section](#how-to) and finally running `git stash pop`.
