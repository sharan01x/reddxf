---
title: "SynthID Is a Trap for Designers"
subtitle: "Watermarking AI content catches the honest and misses the determined — why the binary label is the wrong unit of trust for creative work"
date: 24 Sep 2026
author: sharanx
tags:
  - ai
  - design
image: synthid-header.png
audio: "08d277e1_audio.mp3"
---

Since August 2, 2026, the EU AI Act's Article 50 transparency rules are actually being enforced — machine-readable watermarking on synthetic content, with fines up to €15 million or 3% of global turnover. Google says 100 billion images and videos are already marked with SynthID. Sounds like a win for trust, right?

It isn't. This article (and the video below) make the case that SynthID-style watermarking solves the wrong equation: the people who want to deceive you can strip these marks trivially, while honest designers — the ones using AI for a colour palette, a rough concept, or a first draft — are the ones who get flagged. A lie detector that only beeps at honest people.

## The engineering is real — and misdirected

Let's be fair before we tear into this. SynthID is genuinely impressive engineering, and it is actually a family of techniques, one per medium. For images and video, it embeds a statistical pattern directly into the pixel data — not metadata that can be stripped away with a right click, but invisible alterations to the image itself. For text, it works through logits processors at generation time. The regulatory intent is also understandable: in an era of deepfakes, politicians want a technical solution to point to.

But the engineering is optimising the wrong part of the equation. And if you build things for a living, you know what happens when you optimise for the wrong metric: you build something perfect that makes the problem worse.

## The asymmetry — it catches the honest

Who actually gets caught by watermarking? Run through the threat model. If you're a malicious actor — deepfakes, fake evidence, disinformation farms — weakening a watermark is very doable. For text: paraphrase it, screenshot-and-OCR it, or run it through a model that doesn't watermark; research shows paraphrasing can substantially degrade the signal. For images: pass them through another generative model, compress them hard, crop aggressively. And models that never participated in watermarking at all leave no mark to strip. The tools are already public; there are commercial services that do it for you.

Meanwhile the person who used AI to get unstuck and then spent six hours refining in Illustrator? If any mark survives into the final file, the detector sees "AI involved" — and that's all it sees. The watermark is most likely to still be there on the work of people honest enough to leave it. It's a security guard who only checks IDs of people who voluntarily showed up with IDs.

## The category error — your process is not binary

Watermarking assumes a binary: AI-generated or human-made. But creative process is a spectrum, and the watermark contains zero information about where on that spectrum the work falls.

Consider: you use AI to generate fifty rough logo concepts to get unstuck, pick one, refine it manually for six hours, build the full brand system yourself, revise it seventeen times because the client's nephew had feedback. A surviving mark collapses all of that craft into the same one-bit answer as a single-prompt logo. Meanwhile a photographer who shoots a deepfake displayed on a screen uploads it unmarked and it passes every verification test — the camera didn't generate the deepfake, it just photographed it. Perfectly valid. Completely misleading.

The watermark tells you nothing about craft, intent, or how much human judgment went into the output. It's like judging a restaurant by whether a microwave was used at any point in the process.

## The trust inversion — it makes people less critical

The deeper damage is what watermarking does to how audiences think. If the public settles into "watermarked equals AI equals suspicious, unmarked equals human", the mark becomes an excuse to stop thinking. Unmarked disinformation sails through precisely because it lacks the stamp. There's even a technical failure mode here: C2PA, the provenance standard that complements watermarking, can confirm a camera signed a photo — but it can't confirm the photo wasn't of a screen displaying a deepfake.

Trust is not a technical problem; it's a social one. Watermarking is a technical solution that makes a social problem worse — like installing a very expensive lock on a house with no walls.

## The chilling effect on builders

If you're a designer becoming a builder — using AI to prototype faster, generate code, write documentation — watermarking changes your risk calculus. Every time you use an AI tool you now have to ask: will this mark my work? Will clients devalue it? Will I have to hide my process?

And here's the perverse part: the optimal strategy under watermarking is to use AI and hide it. Strip the mark, rewrite enough to break the signal, claim you did it manually. That's the opposite of transparency — the opposite of the honest process-sharing culture design communities have built. A system where being honest about your process is a professional risk and lying about it is the safe option is not a bug. That's the whole design.

There's a power-dynamics angle too, and it's analysis rather than lab result: watermarking has the shape of regulatory capture dressed up as consumer protection. The companies building the detection tools and compliance infrastructure are the ones best positioned to arbitrate what counts as "authentic". Small creators and open-source runners get squeezed out. It's not a safety feature; it's a moat with very expensive alligators.

## What would actually help

The watermark itself isn't the villain — it's evidence, a genuine signal that a participating tool was involved. The problem is selling it as a verdict. What would actually help:

1. **Process-based provenance, not binary labelling.** Show the chain — AI-assisted ideation, human refinement, human final approval — instead of a single stamp. C2PA can record chains of edits and claims; the chain is only as honest as the tools feeding it, but it respects the spectrum.
2. **Verifiable claims, not origin stamps.** Let creators make signed, checkable claims about their work rather than forcing everything through a one-bit detector.
3. **Media literacy as infrastructure.** Platform-native skepticism training, not a disclaimer blog post everyone scrolls past. We teach people to check URLs before clicking; we can teach them to check claims before believing.
4. **Accept the binary is dissolving.** Build reputation systems, transparent process documentation, and independently verifiable institutional credibility that work regardless of detection.

## The ask

So that's the ask: not ditch the watermarks, but stop selling the binary. Demand tools that show process, not just origin. Treat a detected mark as one data point, not a verdict. And don't let a detector — or the absence of one — do your critical thinking for you.

If you're a designer using AI in your process, I want to hear from you: has watermarking changed how you work? Drop a comment on the video — I read them all.

## Related video

<iframe width="480" height="270" src="https://www.youtube.com/embed/AWDqww6htwQ" frameborder="0" allow="accelerometer; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>