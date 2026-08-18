# How to publish a blog post

Every post is one Markdown file in the `_posts` folder. GitHub rebuilds the site automatically about a minute after you save.

## The three-step version

1. In your GitHub repository, open the `_posts` folder and click Add file, then Create new file.
2. Name it with the date first: `2026-08-25-short-title.md`. The part after the date becomes the URL, so this post would live at galblatman.com/blog/short-title/.
3. Paste the template below, write, and commit. Done.

## The template

```
---
title: "Your title here"
description: "One line shown on the blog index and in previews."
---

Write in plain Markdown. Blank lines separate paragraphs.

**Bold**, *italics*, [links](https://example.com), and lists all work.
```

## Extras

- **Images.** Upload the image to the `assets` folder, then reference it as `![description](/assets/filename.jpg)`.
- **Drafts.** Files in `_drafts` never publish. Write there, and when ready, move the file to `_posts` and add the date prefix to the filename. There is one draft waiting for you now: `_drafts/the-writing-skills.md`.
- **Editing or deleting.** Edit the file in `_posts` and commit; the site updates. Delete the file and the post disappears.
- **RSS.** A feed is generated automatically at `/feed.xml`. Nothing to maintain.
- **With Claude Code.** Open the repository and say what you want: "new post about X, here are my rough notes." It will create the file, format it, and push.

## One rule of thumb

This blog shares a domain with your job market materials. Search committees will find it. The bar for a post is simple: would you be comfortable if it came up in a fly-out dinner conversation? If yes, publish.
