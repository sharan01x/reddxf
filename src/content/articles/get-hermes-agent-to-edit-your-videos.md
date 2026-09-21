---
title: "Get Hermes Agent to Edit Your Videos"
subtitle: "How Hermes Agent fits into every stage of video production — from script and takes to AI-powered editing, titles, captions and export"
date: 21 Sep 2026
author: sharanx
tags:
  - ai
  - video
image: video-editing-header.png
audio: video-editing_audio.mp3
---

Hermes Agent can build the tools you need. In this series, we have already built a custom image generator and a custom audio generation tool. This is the third instalment, and I am changing tack slightly: instead of walking through building a single tool, I want to show how Hermes Agent plays a role in the **entire video production process** — from the first draft of an article to a finished, exported video with titles, captions and background music. The best way to demonstrate that is to actually produce a video and take you through the whole pipeline.

## Everything Starts with an Article

For me, everything starts with an article. I write in Obsidian, my favourite tool for writing, and because everything is markdown, Hermes Agent can read it and edit it directly. Before a script is ever written, I debate the article with Hermes — from multiple perspectives, arguing the weak points until the piece becomes much stronger than my first draft.

That debating habit matters more than it sounds. The article is the source of truth for everything downstream: the script, the titles, the on-screen graphics. If the thinking is muddled at this stage, no amount of clever editing fixes it later.

## From Article to Script

The next step is script creation. The script keeps the essence of the article but re-aligns it for delivery: what I am actually supposed to say, in what order, and with which pauses. It also carries production notes — a reminder that I need a section title card here, a step heading there. Those two layers, the spoken content and the production cues, turn out to be the key inputs for everything the agent does later.

## Recording with a Teleprompter

I read the script from a teleprompter application that reads the script file directly — you pick a script and it shows you the segments you are supposed to say, one by one, on screen. You could build this teleprompter application yourself very easily; that is not the interesting part. What matters is its output: every script segment produces a take.

I rarely get a clean take first time, so I often record multiple takes per segment. To keep track of which take is best, the setup generates a JSON file with a transcript of what was actually said in each take. By comparing that transcript against the script, you can judge how complete each take was — and completion becomes a core part of the editing decision that comes next.

## Two Essential Tools

Two applications do the heavy lifting in this workflow.

**Palmier Pro** is an AI-powered video editor. As a conventional editor it is decent — it has all the core features, though it is not as feature-packed as DaVinci Resolve. Its superpower is that it plugs into Hermes Agent via MCP, the Model Context Protocol, which means you can simply *instruct it to edit your videos*. That saves a tremendous amount of time. DaVinci Resolve has since released a similar agentic feature, but as far as I can tell it is not available in the free version — whereas Palmier Pro is free out of the box, with optional paid add-ons.

**Hyperframes** is a more niche but incredible application. It lets your agent compose motion graphics — think of it as "write HTML, render video". Say you need a motion graphic of a chart for your article: you can point Hermes Agent at the article, and it will create the graph the article requires and render it as a motion graphic. It is incredibly simple once you get your head around it, and an essential part of the production process. I use it constantly.

## Connecting Hermes to the Editor

Here is the actual setup. Palmier Pro is open with the project for this video — the same folder where the teleprompter's recordings live. On the left I have Hermes Agent running (I used GLM 5.3 Flash at the medium setting, though low works just as well).

When getting started with a Palmier Pro project, always establish the MCP connection first. The prompt I give forces the agent to confirm **which project is actually open**. That is the vital part: it makes the agent go through the whole connection handshake — Palmier's MCP server speaks SSE, and so on — and you can verify it actually understood the name of the open project before you trust it with anything else.

Then orient the agent to the project: tell it which project you are working on, where the script lives, and ask it to read both. In my case I asked it to look at a `session.json` file, which records which shots can actually be used, and then import those shots into the Palmier project.

## Importing the Right Takes

This is where the take transcripts earn their keep. The agent examined the markdown files and transcripts, found 45 segments — about the right number — and imported the media into the timeline. Look closely at the result: shot 27 uses take one, shot 28 uses take two, shot 29 uses take three. It compared the transcriptions against the script and picked the right take for each shot automatically.

It even ran a spot inspection using its vision provider. Because I had run out of remote credits, Ollama transparently fell back to a local model and completed the inspection anyway. There were a few gaps in the timeline, which is perfectly expected at this stage — the cut is now ready for titles.

## Titles with Hyperframes

Next, titles. I keep a prompt that asks Hermes to use `video37` — a skill I set up for myself that internally uses the Hyperframes skill — to produce title animations. Each title is generated from the script itself: a section heading like "the engineering is real and misdirected" becomes a title card, rendered with Hyperframes to match the Redd XF channel styling — same colours, same look.

For this video I had already generated and exported the titles, so instead of re-rendering I asked Hermes to import them into the media library *and* place them on the timeline at the right points based on the script, plus apply smooth fade transitions so the titles do not feel abrupt. It did a good job — partly by referencing how I had set things up in the practice projects I ran in preparation, but the concept stands: it would have produced the titles well regardless.

## Captions, Checked Visually

Adding captions comes next. I asked it to insert captions based on the transcriptions and match the channel's styling. It checked whether Barlow, our font, was installed, styled the captions with the channel's look — including the grey backing — and then went one step further: it ran a **visual inspection** to make sure the quality was right.

That last step is the one I appreciate most. As an individual creator, doing all of this with consistent quality every time is incredibly hard. Having a partner in the process that performs precision checks and verifies its own work is worth a lot. It also cleaned up a few wrong imports along the way.

## Background Music and Export

I used the `audio37` tool from the earlier article to produce the background music — it generated a few sample tracks, and I preferred the classical one for this project. I asked Hermes to import that track into the media library and lay it on a new track, with an explicit warning to be careful not to disturb the other tracks, because past imports have occasionally done that. I also asked it to pretend it was doing this for the first time — I did not want it skipping steps because it "remembered" the task. It obliged, narrating every step as if it were the first time, which was funny to watch. The result: the music imported, a new track added and repeated across the timeline, and none of the other tracks affected.

The final steps are export and packaging. I instructed it to export the video into the final folder and to **write the YouTube description**. This is a genuinely handy step: with the timeline established, the agent generates the description, produces the chapter markers — which are always fiddly to make by hand — includes the tags and titles, and writes everything out. The result is the exported video plus a neatly formatted `YouTube-description.txt` sitting in the folder, ready to paste. Everything beautifully done and executed.

## Why Not Turn the Whole Thing into a Skill?

All of these steps could have been packaged into one skill, but there are many manual checks required across the process, so it does not make sense to fully automate it. What Hermes does instead is create the **atomic skills** along the way — how you want captions formed, how your titles are produced — and reusing those already saves a lot of time. This is the most efficient way I have found to produce videos as of today.

## Costs

I checked the logs: the entire production process cost **less than a dollar** in agent costs. Title production ran entirely locally — if you use an external service for that, those would be additional charges. Even if you allowed, say, $10 to produce a video of this nature, that is an incredible cost saving compared with traditional editing workflows — and you are still delivering real value to your audience.

If you have questions about any particular step, let me know — I will fold the answers into this article, so it keeps growing even after the video is published. Happy editing!

## Related Video

<iframe width="480" height="270" src="https://www.youtube.com/embed/Pkxaz4F0NFE" frameborder="0" allow="accelerometer; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>