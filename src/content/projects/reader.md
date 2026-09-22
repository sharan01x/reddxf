---
title: "reader"
subtitle: "EPUB Reader with semantic search, RAG chat, and audio playback"
date: "22 Aug 2026"
author: sharanx
tags:
  - ai
  - reading
  - tools
image: "reader.webp"
client: "Redd Group"
website: "https://github.com/sharan01x/reader"
---

Reader is a modern EPUB reader that goes beyond pagination. Features semantic search across entire books, RAG-based chat for asking questions about the text, and integrated audio playback for listening on the go.

**What it is.** An e-book reading app that treats the book as something you can converse with, not just page through. Standard reader features — a clean reading surface, progress tracking, library management — sit alongside three things most readers don't have: semantic search over the whole book, a chat that answers questions grounded in the text, and built-in audio playback.

**The problem it solves.** Physical intuition doesn't survive digitisation: you can't flip through an e-book to find "that part about the harbour." Text search only helps if you remember the exact words. Reader's semantic search lets you find ideas by meaning — search "the argument about free will" and land on the passage that makes it, however it was phrased. And when a concept doesn't land, you ask the chat instead of re-reading a chapter.

**Who it's for.** Students working through dense texts, researchers cross-referencing books, and heavy readers who want to switch between reading and listening without a second app. Also well suited to language learners using audio plus text on the same book.

**How it works.** Books are indexed with semantic embeddings so search and chat retrieve by meaning; the RAG chat answers from the book's own text with citations to the passage it's drawing from — it explains the book, it doesn't replace it. Audio playback runs from the same index, so listening and reading share progress.

**A concrete use case.** Two hundred pages into a philosophy book, you hit a reference to an earlier claim. Ask the chat "what was the earlier argument about necessity?" — you get the answer with the exact passage cited, and jump straight to it.

**Design note.** The AI features are deliberately subordinate to the reading experience: the text stays centred, the tools stay at the edge, and nothing interrupts a page that doesn't need interrupting.

See the code at [github.com/sharan01x/reader](https://github.com/sharan01x/reader).