# awesome-ai-mine

> The **AI Minefield** — AI model and tool licences read end-to-end, with the clause that matters quoted on each card. The ones we can recommend, and the ones with caveats you should know about before you ship.

Maintained by [Brethof AI](https://brethof.com). Companion to
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

## Contents

- [Commercial Cloud LLM APIs](#commercial-cloud-llm-apis) (2)
- [Open-Weights LLMs](#open-weights-llms) (1)
- [Image Generation Models](#image-generation-models) (7)
- [AI Coding Assistants](#ai-coding-assistants) (1)
- [Video Generation Models](#video-generation-models) (2)

<!-- The list below is generated from entries/*.yaml by scripts/gen_awesome_readme.py. Edit the YAML, not this section. -->

## Commercial Cloud LLM APIs

Cloud LLM APIs you can call from a product without giving up your customers' inputs to the model trainers. The relevant clauses are in the API terms (NOT the consumer privacy policy — those are almost always different on the same provider's website).

- **[Anthropic API (Claude)](https://www.anthropic.com/legal/commercial-terms)** — 🟢 Clean · Commercial Terms 2025 · No training on inputs (default) · Outputs are yours · Zero retention  
  Anthropic does not train on customer API inputs or outputs by default. Zero retention except for a short safety-classification window and the prompt cache. Outputs are yours; commercial use of generated content is allowed. (Different terms apply to the free Claude.ai consumer tier — read that separately.)
- **[Grok (xAI API)](https://x.ai/legal/terms-of-service-enterprise)** — 🟢 Clean · xAI API Enterprise Terms 2026 · 30-day auto-delete · No training (API default) · Consumer tier differs (read separately)  
  API content is auto-deleted within 30 days and not used for training by default; the consumer Grok privacy policy does NOT apply to API data — read the enterprise terms instead. Caveat: the consumer Grok app trains on your public X posts by default outside the EU. The API and the consumer product are two different products with two different deals.

## Open-Weights LLMs

LLM weights you can download and run yourself. Licence variance is the whole point of reading these — "open weights" alone tells you almost nothing about whether you can ship a paid product on them.

- **[Llama 4](https://www.llama.com/license/)** — 🟡 Conditional — MAU threshold · Llama 4 Community License · 700M MAU trigger · Otherwise commercial OK  
  Free for commercial and research use — UNLESS your product, or one of its parent companies, had ≥ 700 million monthly active users at the Llama 3 release date. In that case you need a separate licence from Meta. For everyone else (i.e. almost everyone) this is genuinely commercial-friendly weights.

## Image Generation Models

Image-generation model weights. Mix of Apache 2.0 (commercial OK) and bespoke vendor "Community" licences with revenue caps or non-commercial clauses. The 🟢 / 🟡 pill tells you which.

- **[FLUX.2 [dev] (Black Forest Labs)](https://huggingface.co/black-forest-labs/FLUX.2-dev)** — 🟡 Conditional — non-commercial · FLUX.2-dev Non-Commercial License · 32B flagship · Commercial needs BFL agreement · Pick klein 4B for commercial  
  FLUX.2-dev Non-Commercial License. The 32B flagship of the FLUX.2 family — top output quality, biggest VRAM appetite, and the most restrictive licence of the three (klein 4B is Apache 2.0; klein 9B is non-commercial; dev 32B is also non-commercial). Personal projects, research, fine-tuning experiments OK. Commercial requires a BFL Commercial Use Agreement.
- **[FLUX.2 [klein] 4B (Black Forest Labs)](https://huggingface.co/black-forest-labs/FLUX.2-klein-4B/blob/main/LICENSE.md)** — 🟢 Clean · Apache 2.0 · Full commercial use · Royalty-free · Sibling 9B/dev are NOT Apache (separate entries)  
  Apache 2.0. The 4B variant of FLUX.2 [klein] is released as genuinely open-source — full commercial use, modification, redistribution, royalty-free. Build a paid app, a SaaS, a game with integrated image generation — all OK. Note: the LARGER FLUX.2 [klein] 9B and FLUX.2 [dev] are NOT Apache 2.0 (see separate entries).
- **[FLUX.2 [klein] 9B (Black Forest Labs)](https://huggingface.co/black-forest-labs/FLUX.2-klein-9B/blob/main/LICENSE.md)** — 🟡 Conditional — non-commercial · FLUX Non-Commercial License · Research + personal OK · Commercial needs BFL agreement · 9B capacity costs the open-source bit  
  FLUX Non-Commercial License. The 9B variant gives you the bigger model capacity at the cost of commercial rights — research, personal projects, fine-tuning experiments are allowed; shipping a paid product on these weights is NOT, unless you sign a separate Commercial Use Agreement with Black Forest Labs (their tiered SaaS plan starts at 100K images/month).
- **[Qwen-Image (Alibaba)](https://github.com/QwenLM/Qwen-Image)** — 🟢 Clean · Apache 2.0 · Full commercial use · Self-host OK · Strong text-in-image rendering  
  Apache 2.0. Strong open-weights text-to-image model from Alibaba with notable strength in complex text rendering inside images (a long-standing weak point for diffusion models). Full commercial use, modification, fine-tuning, self-hosted deployment — no restrictions.
- **[Qwen-Image-Edit (Alibaba)](https://huggingface.co/Qwen/Qwen-Image-Edit)** — 🟢 Clean · Apache 2.0 · Full commercial use · Self-host OK · Natural-language image editing  
  Apache 2.0. Alibaba's natural-language image-editing companion to Qwen-Image — instruct it to edit existing images with text prompts. Same permissive licence as the base model: full commercial use, modification, fine-tuning, self-hosted deployment all allowed.
- **[Stable Diffusion 3 Medium / Large](https://stability.ai/community-license-agreement)** — 🟡 Conditional — revenue cap · Stability AI Community License · <$1M revenue commercial OK · Outputs are yours  
  Free for non-commercial use, and for commercial use by individuals and businesses under USD 1 million in annual revenue. Above that revenue threshold you need a Stability AI Enterprise license. Outputs are yours.
- **[Z-Image Turbo (Tongyi-MAI)](https://huggingface.co/Tongyi-MAI/Z-Image-Turbo)** — 🟢 Clean · Apache 2.0 · 6B params (fast) · Full commercial use · Self-host OK  
  Apache 2.0. 6B-parameter text-to-image model from Tongyi-MAI (Alibaba's AI division) optimised for speed — ultra-fast photorealistic generation. Released November 2025 under one of the most permissive AI-model licences in circulation: full commercial use, modification, redistribution, self-hosted deployment.

## AI Coding Assistants

IDE / desktop apps that route your code through a cloud LLM. The terms inherit from the underlying API in most cases — we link the parent entry where that's true.

- **[Claude Code / Claude Desktop](https://www.anthropic.com/legal/commercial-terms)** — 🟢 Clean · Inherits Anthropic Commercial Terms · No code harvesting · Local-client, cloud-inference  
  Code you submit via Claude Code / Claude Desktop is governed by Anthropic's Commercial Terms — same zero-retention and no-training-on-inputs defaults as the raw API. Runs locally on your machine; prompts are sent to Anthropic for inference. No code-snippet harvesting.

## Video Generation Models

Video-generation model weights. New, fast-moving, and the licences are evolving faster than the model architectures. Always re-check the LICENCE file on the model card before you commit to a project.

- **[LTX-2 / LTX-2.3 (Lightricks)](https://huggingface.co/Lightricks/LTX-2/blob/main/LICENSE)** — 🟡 Conditional — multiple clauses · LTX-2 Community License · <$10M revenue commercial OK · Disclose AI-generated content · No competing service · Outputs are yours  
  Free commercial use up to USD 10 million aggregated annual revenue across subsidiaries and affiliates. Required conditions: must disclose AI-generated content to viewers, no deepfakes / impersonation without consent, and you may NOT use it to build a service that competes with LTX-2 video generation. Above $10M revenue you negotiate with Lightricks (liquidated damages clause is 2× retroactive fees if you used it commercially without paying). Outputs are yours — videos can be sold, monetised on YouTube, used in ads.
- **[Wan 2.2 (Alibaba Tongyi Lab)](https://github.com/Wan-Video/Wan2.1)** — 🟢 Clean · Apache 2.0 · Full commercial use · Weights + code open · No vendor lock-in  
  Apache 2.0. Full commercial use, modification, redistribution. No revenue cap, no disclosure requirement, no anti-competition clause. Alibaba publicly released weights, architecture, and code under one of the most permissive open-source licences. Mixture-of-experts video generation, text-to-video and image-to-video.

## Related work

- **[awesome-local-ai](https://github.com/BrethofAI/awesome-local-ai)** — Local-first AI tools (runtimes, chat apps, agents) — many models from this list run there.
- **[awesome-private-ai](https://github.com/BrethofAI/awesome-private-ai)** — Privacy-respecting AI more broadly.
- **[awesome-mcp-servers](https://github.com/BrethofAI/awesome-mcp-servers)** — MCP servers that connect to LLMs from this list.
- **[awesome-linux-for-ai](https://github.com/BrethofAI/awesome-linux-for-ai)** — Linux distros tuned for running these models locally.
- **[awesome-llms-txt](https://github.com/BrethofAI/awesome-llms-txt)** — Tools that publish `llms.txt` for agent discovery.

## Contributing

Open an issue with:

- The model / API / tool name and the canonical licence or ToS URL.
- The exact clause text that decides the verdict (paste it; don't paraphrase).
- Your read of the verdict — 🟢 Clean or 🟡 Conditional + the conditional reason in 1–3 words.
- If you think a tool is missing because it sits in the unlisted-bad-actor pile, please don't open an issue about it — we know, that's the design.

Entries live as one YAML file per tool under `entries/`. This
README is generated from them by [`scripts/gen_awesome_readme.py`](https://github.com/BrethofAI/brethof-website/blob/main/scripts/gen_awesome_readme.py)
in the [`brethof-website`](https://github.com/BrethofAI/brethof-website)
repo — edit the YAML, not this README.

## License

[MIT](LICENSE) on the catalog itself.

The licences of the listed tools belong to their respective vendors
and are linked in each entry — read the original, not our summary,
if you're making a real decision.

---

Maintained by **[Brethof AI](https://brethof.com)** — we read the fine print so you can ship.
