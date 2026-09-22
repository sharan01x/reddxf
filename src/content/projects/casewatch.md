---
title: "This v. That"
subtitle: "A legal case tracker that keeps clients and lawyers on the same page"
date: "20 Jul 2024"
author: sharanx
tags:
  - legal
  - productivity
  - ai
image: "casewatch.webp"
client: "Redd Group"
website: "https://github.com/sharan01x/casewatch"
---

This v. That is a web app to help you keep up with on-going lawsuits. Clients can ask any question about their case without taking up a lawyer's time, while lawyers get instant access to case details — people, timelines and facts — without wading through thousands of pages. Powered by RAG over case documents with AI-assisted discussion, timeline extraction and actor identification.

**What it is.** A case workspace built on top of the documents a lawsuit generates. Case files — filings, evidence, correspondence — are ingested, indexed, and made answerable. Clients ask questions in plain language and get answers grounded in their own case documents; lawyers get structured views of the same material without manual file-digging.

**The problem it solves.** A lawsuit produces thousands of pages, and the people who most need to understand it — the clients paying for it — can't read it all, and shouldn't have to call their lawyer for every "wait, who is this person again?" question. Meanwhile lawyers burn hours relocating facts they half-remember. The gap between the case and the people living through it is a time drain on both sides.

**How it works.** The pipeline runs retrieval-augmented generation (RAG) over the case corpus, so every answer cites the underlying documents rather than inventing plausible-sounding details. Alongside the chat, the system builds structural aids automatically: a case timeline extracted from the filings, and actor identification — who each person in the file is and how they connect — so the case's cast of characters is navigable instead of overwhelming.

**A concrete use case.** A client reads a court notice mentioning a name they've never heard. Instead of a billable phone call, they ask the app: it identifies the person, explains their role in the case, and cites the filing where they first appear — in under a minute.

**Who it's for.** Law practices managing multiple active cases, and their clients, who get transparency without the meter running.

See the code at [github.com/sharan01x/casewatch](https://github.com/sharan01x/casewatch).