---
title: 'Conventions'
date: 2023-11-28T10:10:41-08:00
draft: false

author: 'Matthew Reese'
summary: 'Conventions, style guide, and writing tips.'

weight: 5
---

## English Writing Style

As a preface to this section, these guidelines will in no way be as strict as an English professor would be; however, there are some conventions that should be adhered to for the sake of readability and consistency. I do recommend that all content be put through a grammar and spell checker to ensure correctness before publishing.

- Ensure that all basic grammar rules are followed and words are spelled in standard American-English. This should not become anything pedantic so just use common sense.
  - What matters: run-on sentences, misspelled words, any grammar that's clearly and obviously wrong to the average reader.
  - What doesn't really matter: misuse of colons or hyphens, sentences that are a bit wrong but still perfectly understandable.
- No colons in headers. The formatting of a header **already** denotes that the content following will be *under* that header. There's no need to be repetitive.
- Limit use of first-person pronouns ("I", "me", "we", etc.) When writing a how-to guide or similar piece of content, repetitive use of these can become very boring to read.

## Markdown Style

Each and every file will be run through a markdown linter so that code is standardized and readable. If you're using VSCode, here's [a great extension](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint) to install. For external editors, here's an [node.js application](https://github.com/DavidAnson/markdownlint) by the same developer.

- One small convention 

## Writing Tips

Some of these may be obvious so take away what you will from this section. Understand that the end-goal of this content is to be **understandable by a first-year computer science student**. That being said, not everything has to *quickly* comprehended; you may write a series of long explanations in order to introduce a complex topic, when the topic is normally miles above what a first-year students would normally learn.

- Make use of many, many examples. Each introduction of a new topic should come with **at least** one example.
- Images, graphs, and videos are worth 1000 words. So are code snippets.
- Pause in the midst of your explanations once in while and reflect upon the bigger picture (i.e. how one sub-concept applies to the larger one). It may even be helpful to ask the reader to think about this, or have them try to solve a problem for a better understanding.
- Links are great, and should be used often. Remember though: not all sites are written with the same readers in mind. Also, be sure to **actually read through the entire source yourself**. Do not assume that an external site has useful and relevant content by just glancing at it.
- Be conscious of the words you use to describe something, do not attempt to explain a concept in a convoluted way to avoid using more advanced terms. If necessary, define the terms, then use them in context. For example, a python list could be defined as *"an ordered set of values of any type that can be changed"* but could be said a lot more simply as *"an ordered set of **mutable** values of any type"*. (The term *heterogeneous* might even be used, but there's a fine line that needs to be drawn somewhere).

At risk of stating the extremely obvious, ensure that content uploaded is your own, and only your own. If you wish to refer to an outside source, provide a link. If it is absolutely necessary that you provide a code sample from an outside source, ensure that the author is properly attributed to.

One more rather obvious note: if you just learned about the content from a single source, do not attempt to write about it in an educational way; it will not go well. Firstly, there's the implicit bias that stems from having gathered information from a single place. Without an introduction to other sources, or experience working with the concepts/systems, that one source will be treated as the gospel truth. Another perhaps more compelling reason, is that there is no way to understand the many nuances of a concept/system without seeing it from numerous perspectives, and working with it yourself.

Lastly and most importantly, make it interesting and make it fun. Put some personality into your writing, crack a joke here and there, and make sure it's not mind-numbingly boring.

___

Here is an amazing video on methods for writing this type of content, many of which are directly applicable to this site. The timestamp that it starts on specifically discusses the prevalent design problems and solutions for puzzles, but also has merit for teaching in any form.

{{< youtube "gibVyxpi-qA?start=891" >}}