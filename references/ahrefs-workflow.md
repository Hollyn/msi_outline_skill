# Ahrefs workflow

The exact calls that produce the data layer for a brief. All examples are verified
against the live Ahrefs MCP connection.

Every call needs `country` (two-letter ISO code, e.g. `us`) and `select` (a
comma-separated list of columns). If you are unsure which columns an endpoint
supports, call `doc` with the tool name first — it returns the real schema.

## 1. Keyword metrics

```
keywords-explorer-overview
  keywords: <target keyword>
  country:  us
  select:   keyword,volume,difficulty,traffic_potential,parent_topic,
            parent_volume,cpc,intents,serp_features,global_volume
```

What each field is for:

- **volume / global_volume** — scale of the opportunity.
- **difficulty** — Ahrefs' 0–100 estimate of how hard the top 10 is.
- **traffic_potential** — total traffic the #1 page gets from *all* its keywords.
  Frequently several times the keyword's own volume; that ratio tells you how
  broadly to scope the post.
- **intents** — booleans for informational / navigational / commercial /
  transactional / branded / local. This is Ahrefs' own read of underlying
  intent. Use it as a cross-check on your SERP reading, not a replacement:
  if you called the SERP transactional and Ahrefs says informational, look again.
- **serp_features** — the feature set on the SERP (`image`, `video`,
  `discussion`, `ai_overview`, `snippet`, `question`…). Cheapest way to detect
  visual, video or forum intent before you read a single page.
- **parent_topic / parent_volume** — see below.

### The parent-topic check

`parent_topic` is the keyword driving the most traffic to the current #1 page.
When it differs from the target keyword and carries materially more volume, the
same post can usually rank for both by targeting the broader topic.

Do not swap the keyword — it was decided upstream by keyword research. Flag it
in the brief and let the reviewer decide. Phrase it as evidence, not a
recommendation:

> Parent topic is "homeschool room" (1,000/mo) vs the target's 250/mo. One post
> can serve both; consider widening the H1 beyond "DIY" to capture the parent.

## 2. The ranking table

```
serp-overview
  keyword:       <target keyword>
  country:       us
  type:          organic
  top_positions: 10
  select:        position,url,title,domain_rating,url_rating,refdomains,
                 backlinks,traffic,keywords,page_type
```

**Always pass `type: organic`.** Without it the endpoint returns every SERP
element — each AI-overview sitelink and image-pack thumbnail comes back as its
own row at position 1 or 2. On a verified test this was 39 rows and 1,014 API
units, versus 7 rows and 140 units with the filter. Same ranking table, an
eighth of the cost.

Read `serp_features` from step 1 for the feature picture instead; that is what
it is there for.

Two columns do most of the diagnostic work:

- **`page_type`** — Ahrefs' predicted page type as a slash path, e.g.
  `/Article,/Article/Listicle` or `/Article/How_to`. This is content format
  handed to you directly. It is null for social and UGC pages, which is itself
  informative.
- **`refdomains` / `domain_rating`** — the authority-vs-merit test. A thin page
  ranking on hundreds of referring domains is ranking on links; do not copy its
  structure. A page ranking at DR 1 with zero referring domains is ranking
  purely on content fit, and is the most instructive page on the SERP.

### Reading the position gaps

Positions are absolute SERP slots, so `type: organic` leaves gaps. If the first
organic result is position 3, positions 1 and 2 went to an AI overview and an
image pack. Count the gaps and say so in the brief — three of the top ten slots
being non-organic changes what ranking there is actually worth.

### Ranking viability

Ron's working rule for a newer site: at least three competitors in the top 10
with DR under 30, and low referring-domain counts among them. Check it against
the table and state the result. It is a sanity check on the keyword, not a veto
— the call belongs to the reviewer.

## 3. Secondary keywords

```
keywords-explorer-matching-terms
  keywords:   <target keyword, or the parent topic>
  country:    us
  match_mode: terms
  select:     keyword,volume,difficulty,cpc
  order_by:   volume:desc
  limit:      15
```

Query the **parent topic** rather than the exact target when one exists — it
returns the wider cluster the post can serve.

`keywords-explorer-related-terms` and `keywords-explorer-search-suggestions`
cover the same ground from different angles; reach for them when matching-terms
comes back thin.

Every secondary keyword in the brief needs a named home — a specific H2, the
FAQ block, the intro. Placement, never density targets.

## 4. Cost

Roughly 20–26 units per returned row, so a full brief costs about 500–1,000
units. Ron's plan carries 400,000 units a month, which is several hundred
briefs — comfortable, but not a reason to pull data you will not use. Check the
remaining budget with `subscription-info-limits-and-usage`, which is free.

Calls containing only the literal words `ahrefs` or `wordcount` as the keyword
are also free, which makes them useful for testing that the connection is live.

## What Ahrefs cannot tell you

`serp-overview` returns a cached snapshot, and `update_date` is often weeks or
months old. It is the right source for metrics and for the shape of the SERP,
and the wrong source for what is ranking *today*.

It also does not contain page bodies. The headings, sub-topics and actual
argument of each competing page come from reading them. Ahrefs tells you which
pages to read and which to discount; step 1 of the skill is still the work.
