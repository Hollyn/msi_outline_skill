# Search intent: type, format, angle

Reconciled against the in-house Keyword Research SOP (Monday.com, "Step #2:
Identify the Keyword's Search Intent, Parent Topic, and SERP Features"). The
tooling screenshots in that document are dated; the principles below are the
house position and are current.

Search engines have spent enormous effort modelling why someone searches a given
phrase and what they expect back. What appears on a SERP is what they have
already concluded users want. Matching that expectation is a precondition for
ranking, not an optimisation on top of it — an unmatched page does not rank
slightly worse, it does not rank.

Read all three dimensions off the live SERP. The SERP is the answer key.

**The house rule: follow the crowd on type, format and angle, but do not copy
them.** Stick to what the data says the shape should be, then differentiate
inside that shape. Trying to rank a how-to when everything ranking is an opinion
piece wastes the post.

## Underlying intent

Five categories, and a keyword can carry more than one:

- **Informational** — wants to know something. Most blog posts.
- **Navigational** — wants a specific site or page.
- **Commercial investigation** — comparing, close to buying, not there yet.
- **Transactional** — ready to buy.
- **Local** — wants somewhere nearby.

Ahrefs returns its own read of these as booleans on
`keywords-explorer-overview`. Use it to check your SERP reading, not to replace it.

## Content type

Four categories: blog post, category page, product page, landing/home page.

Search "Nike running shoes" and the results are product and category pages from
e-commerce sites. Search "potato pancakes" and the results are recipe blog posts.

**This one is a hard gate.** If the SERP for your keyword returns predominantly
product or category pages, a blog post will not rank for it, no matter how well
written. Flag it and stop rather than producing an unusable brief.

## Content format

How the content is packaged. The common ones: how-to guides, step-by-step
tutorials, list posts, opinion pieces, reviews, comparisons.

Read it off the titles. "Best email marketing tools" returning "28 best", "16
best", "7 best" is a SERP that wants a listicle and will not take anything else.
"Blogging for profit" returning a mix of "how to start" guides and "15 ways"
listicles means either works, and a guide-shaped listicle may fit best.

Ahrefs' `page_type` column on `serp-overview` gives its own classification
(`/Article/Listicle`, `/Article/How_to`). Corroborate with it; don't outsource
the call to it.

## Content angle

The house definition: the unique selling point of the top-ranking pages, and
therefore an insight into what searchers value when making this particular
search. It shows up as words recurring across ranking titles.

"SEO tactics" returns *traffic-generating*, *drive organic traffic*, *increase
organic traffic*, *new techniques*. Two angles are doing the work: **more
traffic** and **new or unique**.

"Tent for winter camping" returns *best* and detailed reviews, with *insulated*
recurring. The angle is quality and insulation. Price, discounts or shipping
would be the wrong angle to lead with here, because that is not what is ranking.

Combine the three into a working title before outlining. "How to start" (angle:
beginners) plus listicle plus guide gives you *a 15-step guide for new bloggers*.

## SERP features are a traffic question, not just an intent signal

Features sit above the organic results and take clicks that would otherwise
reach them: featured snippets, People Also Ask, video panels, image packs, map
packs, top stories, knowledge panels and cards, ads. The SOP's example is "how
to tie a tie" — a featured snippet and a video panel appear before a single
organic result, so even position 3 earns far less than the rank suggests.

AI overviews are the current version of this problem and the most aggressive one.
The SOP predates them; the principle covers them exactly.

So identify the features, name them in the brief, and say which of three things
follows:

1. Rank normally, because the features are minor.
2. Optimise deliberately for the feature — a question-shaped heading with a
   direct answer beneath it to win the snippet or the AI citation.
3. Question whether the keyword is worth the post at all, because the features
   take most of the traffic.

That third option is a real answer. Say it when it is true.

## Parent topic

`parent_topic` is the keyword sending the most traffic to the current #1 page.
It answers whether Google sees your keyword as its own topic or part of a larger
one, which decides whether this is one page or two.

Three outcomes:

- **Parent equals the keyword.** Nothing to do.
- **Parent is broader and the keyword is a subtopic of it.** One page targeting
  the parent, with the keyword covered as a section inside it.
- **Both justify a page.** The narrower term has enough distinct intent and
  traffic of its own. Cover the broad topic on one page, the specific one on
  another, and link between them so the authority is shared.

The SOP's example: "blogging services for small business" has the parent
"blogging for small business", but a page in position 6 targets the narrow term
and around half the results draw most of their traffic from it. Both pages are
warranted.

The house SOP allows changing the primary keyword to the parent at the keyword
research stage. **By the time a keyword reaches this skill that decision is
made.** Do not change it here. Flag the parent, state the volumes, recommend, and
let the reviewer decide.

## Ranking on authority vs ranking on merit

A page can rank while breaking every structural rule if it has enough backlinks.
When a top result has no heading structure and hundreds of referring domains,
that is what you are seeing.

Do not copy its structure. Note it in the brief, and take structural signal from
the pages ranking without that backlink advantage — a page ranking at DR 1 with
zero referring domains is the most instructive result on any SERP.
