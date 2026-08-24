---
name: seo-content-brief
description: Produce an SEO-optimized content outline (brief) for a target keyword — competitor SERP analysis, search-intent matching, heading hierarchy, and instructional bullets for the writer. Use this skill whenever the user asks for a content brief, blog outline, article outline, post structure, SEO outline, or "what should this article cover" — and also whenever they hand over a keyword and a word count and expect a plan for a piece of content, even if they don't use the word "outline". Do not freehand an outline from general knowledge; always run this process.
---

# SEO Content Brief

Produce the outline a writer receives before they write a word. The outline is the single biggest lever on the quality of the finished post — it decides what ranks, what the reader gets, and what the writer is aiming at.

This skill does not write the post. It produces a structural plan with instructional guidance, which an experienced human reviews, cuts, reorders and hands to a writer who retains full creative control.

## Inputs

**Target keyword** — required. Decided upstream by keyword research. Do not substitute a keyword you think is better; if you spot a problem with it, flag it in the output and continue.

**Word count** — ask for it, but do not block on it. If nobody supplies a figure, derive one from the average length of the pages currently ranking and state clearly in the output that you did so, and what the average was. Word count governs how many headings the outline can support: a 1,000-word post with 30 headings is worthless, because every section ends up surface-level.

**ICP / brand notes** — effectively required for step 6. Without knowing who the brand serves and what it knows that others don't, the "unique angle" degrades into a generic content gap that any competitor could also fill. If these notes aren't available, produce the brief anyway but say plainly in the output that the angle is provisional and needs brand input before it goes to a writer.

Genuinely optional, but valuable if offered: founder or SME notes with a specific take, internal links to include, and the CTA the post should land on.

## Process

### 1. Read the live SERP

Search the target keyword and read the top 10 organic results properly — not the snippets, the actual pages. Skip ads and note (but don't count) AI overviews.

For each page capture: the H1, the full heading hierarchy, the sub-topics covered, the apparent publish or update date, and anything conspicuously common across pages.

Recurring elements across ranking pages are signal, not coincidence. If five of the top ten organise around a numbered list of ideas, that structure is part of why they rank.

**Also record what else occupies the SERP besides ordinary articles.** Image packs, video results, Pinterest boards, YouTube, forums, or a People Also Ask block are all ranking signals about what the searcher wants delivered.

Pinterest or an image pack on page one means the query carries **visual intent** — people want to see the thing, not read about it. A text-first post underperforms on those keywords no matter how well structured. When you see this, say so explicitly in the output and flag it for the design team: the post needs substantial original imagery with real alt text, and that requirement needs to be known before the writer starts, not after.

Video results suggest demonstration intent; heavy forum presence suggests the searcher wants candid experience rather than a polished guide. Note whichever applies and let it shape the recommendation.

### 2. Pull the data layer

Use the Ahrefs connection to pull the top 10–20 ranking pages for the keyword, plus keyword difficulty, search volume, traffic potential, secondary and related keywords, and referring domains per ranking page.

Referring domains matter for diagnosis: a thin, badly structured page ranking at #1 with hundreds of backlinks is ranking on authority, not on structure. Do not copy its structure. Say so in the output.

### 3. Match search intent — do this before building anything

Search intent is the gate. Get it wrong and no amount of quality makes the page rank. Three dimensions, all read off the SERP:

**Content type** — blog post, category page, product page, or landing/home page. If the SERP returns predominantly product or category pages, a blog post will not rank for this keyword, however good it is. Stop and flag this to the user rather than producing an outline that cannot succeed.

**Content format** — how-to guide, step-by-step tutorial, listicle, opinion piece, review, comparison. Read it off the titles. "28 best", "16 best", "7 best" is a SERP telling you it wants a listicle.

**Content angle** — the recurring hook in the titles. "How to start" signals a beginner audience. "New", "more traffic", "insulated" are angles the searcher is actually selecting for.

State all three explicitly in the output, with the evidence from the SERP that supports each.

### 4. Build the outline

Structure with a proper hierarchy — one H1, H2s for core topics, H3s for their sub-topics, H4s only where genuinely needed. Google reads hierarchy; so do AI answer engines.

Sequence matters as much as coverage. Order sections so each one earns the next, and so a reader who stops halfway has still got something.

Apply the reverse pyramid: if the keyword poses a question, answer it near the top, in plain terms, before elaborating. Skimmers and AI answer engines both take the answer from there.

Under each heading write **instructional bullets** — what the writer should cover and why it matters. Not prose, not draft sentences. The writers are subject experts; they need direction and narrative intent, not words put in their mouths.

See `references/outline-format.md` for the exact shape and a worked example.

### 5. Optimize against five lenses

In priority order:

1. **Reader value** — does someone who reads this get the thing they came for?
2. **SEO** — intent match, hierarchy, secondary keyword placement, coverage of what's actually ranking.
3. **AEO** — is the answer extractable? Clear question-shaped headings, direct answers underneath, definitions and lists that an AI engine can lift cleanly.
4. **UX** — scannable, sensible section lengths, no wall-of-text stretches.
5. **ICP fit** — does the framing speak to this brand's actual buyer, and does the CTA follow naturally from the content?

Conversion sits inside ICP fit and UX: the post should lead somewhere without being a sales page.

### 6. Add a genuine angle

The core failure mode is a competent rehash of the top ten. Take the ranking factors and structural patterns that are working, but the outline must also carry something the existing results don't have.

A real angle almost always comes from the brand's own position — what this client sees that the generalist publishers writing the ranking pages do not. A gap you can spot from the SERP alone ("nobody covers X") is a weaker angle, because any competitor reading the same SERP can spot it too. Use the ICP and brand notes here; if you don't have them, name the angle as provisional rather than presenting a generic gap as a differentiator.

Where that angle should come from the writer's own experience or the client's data, do not invent it. Mark the place and say what kind of input belongs there — for example: "Writer: insert a concrete example from a real classroom setup here; the ranking pages are all generic."

Never fabricate statistics, case studies, quotes, or client results to fill this gap.

## Output format

Use this structure:

```
# Content Brief: [keyword]

**Target keyword:** [keyword]
**Word count:** [n]
**Search intent:** [type] / [format] / [angle]

## Intent analysis
[What the SERP shows and the evidence for the three intent calls. Note
any page ranking on backlinks rather than merit, and any reason this
keyword may be a poor fit for the intended content type. Call out
SERP features — image packs, Pinterest, video, forums — and what they
imply about how this post needs to be delivered.]

## Competitive picture
[What the top results have in common, where the gaps are, what to beat.]

## Recommended outline

### H2: [heading]
- [instructional bullet]
- [instructional bullet]

#### H3: [subheading]
- [instructional bullet]

[...]

## Why this sequence
[Short justification of the order and hierarchy — what each section
sets up, and why the answer sits where it does.]

## Unique angle
[The differentiator, and any placeholders needing writer or SME input.]

## Secondary keywords
[Terms with a natural placement — FAQ, intro, a given section.
Placement, not density targets.]
```

## Handing off

The output is a draft for a human reviewer, not a finished artifact. Expect them to cut sections, reorder, and overrule the reasoning — that is the design, not a failure.

Two habits make review fast: give the reasoning inline so a reviewer can disagree with a specific claim rather than the whole document, and keep the heading count proportionate to the word count so cuts are a judgement call rather than a necessity.

## Reference files

- `references/outline-format.md` — the exact outline shape, worked example, and what makes a good instructional bullet.
- `references/search-intent.md` — extended guidance on type, format and angle. Read this whenever the intent call is not obvious from the SERP.
