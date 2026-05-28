# awesome-ai-minefield

> The **AI Minefield** — AI model and tool licences read end-to-end, with the clause that matters quoted on each card. The ones we can recommend, and the ones with caveats you should know about before you ship.

> *Renamed from `awesome-ai-mine` on 2026-05-28. GitHub redirects the old URL.*

Maintained by [Brethof AI](https://brethof.ai). Companion to
[awesome-private-ai](https://github.com/BrethofAI/awesome-private-ai)
and [awesome-local-ai](https://github.com/BrethofAI/awesome-local-ai).

## Why this list exists

The legal surface area of modern AI tooling is hostile by default.
"Open weights" sometimes means "non-commercial only." "Open source"
sometimes covers a permissive client and a closed cloud. ToS pages
update without changelog entries. Free-tier consumer products
routinely train on your inputs; paid API tiers of the same products
routinely don't — but the toggle is buried somewhere in a different
document.

This list catalogues, **for each tool that earned a spot here**, the
four questions that actually matter:

1. **Will this tool train on my data?** *(retention + use-for-training)*
2. **Can I use it commercially?** *(weights / models / output)*
3. **Who owns the outputs?** *(IP assignment)*
4. **Am I indemnified if the model regurgitates copyrighted material?**

We quote the load-bearing clause directly on each card. We do not
paraphrase. We do not editorialise. The licence is the source.

## How to read the cards

Every entry has a verdict pill as its first tag:

- **🟢 Clean** — recommend without caveats. Full commercial use is OK
  out of the box. Examples: Apache 2.0 weights; Anthropic API where
  zero-retention + no-training is the default tier behaviour.
- **🟡 Conditional** — usable, but a specific clause matters. The
  pill tells you what (`revenue cap`, `non-commercial`, `disclose AI`,
  `no competing service`, etc). Read the tagline before you ship.

There is no 🔴 tier on this list. If the answer to "can a small
business ship a product on this without paying or asking?" is "no
for hostile reasons" (e.g. mandatory training on your inputs, broad
IP claims on your outputs, default-public data harvest), the tool
is **not** on this list. We don't explain those omissions — this
isn't a critique blog, it's a recommend list.

## Inclusion rules

To be listed:

- We read the actual licence / ToS, not a vendor blog summary.
- The load-bearing clause is quoted directly in the entry.
- A small commercial team could ship on it — either freely (🟢) or
  with a clearly-stated condition (🟡).
- Maintained — the licence URL still resolves; the model / API still
  exists; the terms quoted are current as of the entry's `added` date.
- We re-check entries opportunistically. Vendors edit licences without
  notice — if you spot drift, open an issue.

## Disclaimer

Not legal advice. We read these licences carefully and quote them
directly, but we are an AI marketing team, not your lawyers. For
anything you're betting your business on, have an actual attorney
look at the terms.
