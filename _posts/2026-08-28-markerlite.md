---
title: "markerlite"
description: "A small converter that turns academic PDFs into Markdown before they enter an AI context window."
tags: [tools]
date: 2026-08-28 09:00:00 -0700
---

When you give Claude a PDF, it processes both the document's extracted text and images of its pages. That is useful when the page itself matters. For most of what I do with academic papers, it does not. I want the text, in the right order, with enough structure for the model to know what it is reading.

So I made **markerlite**.

It is a small local app that converts academic PDFs to Markdown before I hand them to a model. Drop in a paper and it reconstructs reading order across columns, removes much of the running page furniture, identifies headings and footnotes, and attempts to recover tables and captions from the PDF's text layer. Under the hood it borrows heavily from [Marker](https://github.com/datalab-to/marker), the excellent open-source converter; the table-reconstruction module is vendored from it directly, under Apache-2.0.

![The markerlite window: files and per-file status on the left, the converted Markdown previewed on the right.](/assets/markerlite-gui.png)

The payoff is mostly context. One 18-page report I tested became roughly 6,500 tokens of structured Markdown. If I only need the paper's content, I would rather spend those tokens on the text than on reconstructing eighteen rendered pages.

Figures can be extracted as separate files. Equations are harder: PDF text layers often preserve their glyphs without preserving the mathematical structure that made them an equation. markerlite therefore has an option to crop likely equation regions so they can be transcribed separately, by hand or with a vision model, and inserted back into the Markdown.

It works best on born-digital PDFs. Scanned papers can go through Tesseract, and complicated tables, unusual layouts, and equations are still the places most likely to need checking. The preview is there for a reason.

[markerlite is on GitHub](https://github.com/GalBlatman/markerlite). It runs locally and does not send the paper anywhere. Setup notes are included for the Windows app and command-line use. There is also a Windows build that needs no Python install, on the repository's Releases page. It is not code-signed, since signing certificates cost real money, so Windows will show a "Windows protected your PC" dialog the first time: click More info, then Run anyway. If you would rather read the code than trust a dialog, that is what the repository is for. The vendored module keeps Marker's license; for the rest, as with the review skill, write to me before redistributing or adapting.

If it chokes on a layout, send me the PDF. Layouts I have not met are how it improves.
