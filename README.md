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
  no-training is the default and inputs/outputs are deleted within 30 days.
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

<!-- LIST:START -->
## Contents

- [Commercial Cloud LLM APIs](#commercial-cloud-llm-apis) (3)
- [Open-Weights LLMs](#open-weights-llms) (10)
- [Image Generation Models](#image-generation-models) (8)
- [AI Coding Assistants](#ai-coding-assistants) (1)
- [Video Generation Models](#video-generation-models) (2)

<!-- The list below is generated from entries/*.yaml by scripts/gen_awesome_readme.py. Edit the YAML, not this section. -->

## Commercial Cloud LLM APIs

Cloud LLM APIs you can call from a product without giving up your customers' inputs to the model trainers. The relevant clauses are in the API terms (NOT the consumer privacy policy — those are almost always different on the same provider's website).

- **[Anthropic API (Claude)](https://www.anthropic.com/legal/commercial-terms)** — 🟢 Clean · Commercial Terms (effective 2025-06-17) · No training on inputs (default) · Outputs are yours · 30-day retention (ZDR by agreement)  
  Anthropic does not train on customer API inputs or outputs by default: "Anthropic may not train models on Customer Content from Services." Outputs are yours: "Customer (a) retains all rights to its Inputs, and (b) owns its Outputs." Retention is NOT zero by default — per Anthropic's Privacy Center, "we automatically delete inputs and outputs on our backend within 30 days of receipt or generation", with exceptions (e.g. Files API, usage-policy enforcement, law); zero data retention requires a separate agreement (https://privacy.claude.com/en/articles/7996866). Commercial use of generated content is allowed. (Different terms apply to the free Claude.ai consumer tier — read that separately.)
- **[Google Gemini API / AI Studio](https://ai.google.dev/gemini-api/terms)** — 🟡 Conditional — free tier trains on your data · Gemini API Additional Terms (2026-03-23) · Paid tier no training · EEA / CH / UK free tier treated as paid · No competing models  
  Gemini API Additional Terms (effective 2026-03-23). Training depends on whether you pay. Unpaid Services (AI Studio, free quota): "Google uses the content you submit to the Services and any generated responses to provide, improve, and develop Google products and services and machine learning technologies", human reviewers may read it, and "Do not submit sensitive, confidential, or personal information to the Unpaid Services." Paid Services: "Google doesn't use your prompts (including associated system instructions, cached content, and files such as images, videos, or documents) or responses to improve our products"; prompts are logged for a limited period for abuse detection. The API is paid "only when accessing the API through a Cloud Project associated with an active billing account". In the EEA, Switzerland and the UK the paid-tier data terms "apply to all Services, including Google AI Studio and unpaid quota in the Gemini API". Outputs: "Google won't claim ownership over that content." You "may not use the Services to develop models that compete with the Services".
- **[Grok (SpaceXAI API, formerly xAI)](https://x.ai/legal/terms-of-service-enterprise)** — 🟢 Clean · SpaceXAI Enterprise Terms (2026-08-14) · 30-day auto-delete · No training (API, subject to settings) · Consumer tier differs (read separately)  
  xAI now contracts as "SpaceXAI LLC" (Enterprise terms last updated 2026-08-14). API content is not used for training: "SpaceXAI will not use any User Content to train any foundation models, large language models, or other artificial intelligence systems" — note the clause continues "subject to disclosures to Customer and Customer-controlled user settings", so check your console settings. Retention: "All User Content will be automatically and permanently deleted no later than 30 days after the end of the interaction or session", unless a different period is agreed or legally required. Customer "owns all right, title, and interest in the Output". The consumer Grok privacy policy is a different deal: it says the service uses public X posts "to develop and improve our Service" (https://x.ai/legal/privacy-policy).

## Open-Weights LLMs

LLM weights you can download and run yourself. Licence variance is the whole point of reading these — "open weights" alone tells you almost nothing about whether you can ship a paid product on them.

- **[DeepSeek-V4.1-Flash (DeepSeek)](https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash/blob/main/LICENSE)** — 🟢 Clean · MIT · Full commercial use · No revenue or MAU threshold · Self-host OK  
  MIT License (released 2026-09-10; the V4-Flash and V4-Pro checkpoints from July–August 2026 are also tagged MIT). "Permission is hereby granted, free of charge, to any person obtaining a copy of this software ... to deal in the Software without restriction" — the only condition is keeping the copyright and permission notice. No revenue cap, no MAU trigger, no service-type exclusion, no attribution beyond the notice. Self-hosting is the clean path; DeepSeek's hosted API has its own terms, which this entry does not cover.
- **[Gemma 4 (Google DeepMind)](https://ai.google.dev/gemma/apache_2)** — 🟢 Clean · Apache 2.0 · Full commercial use · Self-host OK · Gemma 3 and older stay on Gemma Terms of Use  
  Apache 2.0 — a break from the custom Gemma Terms of Use that covered Gemma 3. Google's Gemma 4 licence link (ai.google.dev/gemma/docs/gemma_4_license) now redirects to the plain Apache License 2.0, and every Gemma 4 card is tagged license: apache-2.0: a "perpetual, worldwide, non-exclusive, no-charge, royalty-free, irrevocable copyright license". No revenue cap, no MAU trigger, no attribution beyond the notice. Sizes from E2B / E4B (on-device) through 12B, 26B-A4B (MoE) and 31B, multimodal input, up to 256K context — small enough to self-host on one GPU.
- **[GLM-5.3 (Z.AI)](https://huggingface.co/zai-org/GLM-5.3/blob/main/LICENSE)** — 🟢 Clean · GLM-5.3 License (modified MIT) · Security review only for MaaS businesses above $10B revenue · GLM-5.3-Flash is plain MIT  
  GLM-5.3 License (released 2026-08-25) — MIT-style grant with one condition that only bites at hyperscaler size: "If the Licensee or any of its affiliates operates a Model as a Service business, and the aggregate revenue of the Licensee and its affiliates exceeds 10 billion US dollars ... the Licensee must pass Z.AI's security review before using the Software or its derivative works for any commercial purpose." For everyone else: commercial use, fine-tuning and redistribution with the copyright notice kept. The smaller GLM-5.3-Flash (and GLM-5.2) are plain MIT.
- **[gpt-oss-120b / gpt-oss-20b (OpenAI)](https://huggingface.co/openai/gpt-oss-120b/blob/main/LICENSE)** — 🟢 Clean · Apache 2.0 · Full commercial use · Self-host OK  
  Apache 2.0 (released August 2025), plus a one-line usage policy shipped alongside: "By using OpenAI gpt-oss-120b, you agree to comply with all applicable law." No revenue cap, MAU trigger, attribution or service-type exclusion. The 20B variant runs on a single consumer GPU or a laptop with enough memory; the 120B on one 80GB GPU. OpenAI's hosted API is a separate product with separate terms.
- **[Kimi K3 (Moonshot AI)](https://huggingface.co/moonshotai/Kimi-K3/blob/main/LICENSE)** — 🟡 Conditional — MaaS revenue cap + attribution · Kimi K3 License (modified MIT) · MaaS over $20M revenue needs agreement · "Kimi K3" attribution above 100M MAU / $20M monthly revenue · Internal use exempt  
  Kimi K3 License (modified MIT, released 2026-06-13). Two conditions. Inference-API businesses above a revenue line need a deal: "If the Licensee or any of its affiliates operates a Model as a Service business, and the aggregate revenue of the Licensee and its affiliates exceeds 20 million US dollars ... the Licensee must enter into a separate agreement with Moonshot AI". And attribution at scale: above 100M MAU or US$20M monthly revenue, "Kimi K3" must be prominently displayed on the user interface. Neither applies to internal use, or to end-user products where model capabilities are "solely embedded within specific features". Otherwise commercial use, fine-tuning and redistribution are allowed.
- **[Llama 4](https://dev.meta.ai/llama/llama4/license)** — 🟡 Conditional — MAU threshold + attribution + EU exclusion · Llama 4 Community License · 700M MAU trigger (Llama 4 release date) · "Built with Llama" required · No multimodal rights for EU-based licensees  
  Llama 4 Community License (effective 2025-04-05). Commercial use is free unless you are huge: "If, on the Llama 4 version release date, the monthly active users ... is greater than 700 million monthly active users in the preceding calendar month, you must request a license from Meta" (counted across you and your affiliates). Two more conditions most teams do hit: attribution — you must "prominently display “Built with Llama”", and a model trained or fine-tuned on Llama outputs must "include “Llama” at the beginning of any such AI model name"; and an EU exclusion in the Acceptable Use Policy — for multimodal Llama 4 models, rights "are not being granted to you if you are an individual domiciled in, or a company with a principal place of business in, the European Union" (end users of a product built on them are not affected; https://dev.meta.ai/llama/llama4/use-policy). Note: llama.com/license now redirects to the Llama 2 licence — link the Llama 4 page.
- **[MiniMax-M3 (MiniMax)](https://huggingface.co/MiniMaxAI/MiniMax-M3/blob/main/LICENSE)** — 🟡 Conditional — attribution + notice / authorization · MiniMax Community License · "Built with MiniMax M3" required · Notice below $20M revenue, written authorization above · No military use  
  MiniMax Community License (released 2026-06-02). The base grant is "for non-commercial purposes"; commercial use is allowed on conditions: you "shall prominently display “Built with MiniMax M3”", and you must email MiniMax — a one-time notice below US$20M yearly revenue, "a separate, prior written authorization" above it. "Commercial Use" explicitly includes offering it via APIs or hosted services. An appended Prohibited Uses list includes any "military purpose". Read the whole thing before shipping.
- **[Mistral Small 4 (Mistral AI)](https://huggingface.co/mistralai/Mistral-Small-4-119B-2603)** — 🟢 Clean · Apache 2.0 · Full commercial use · Self-host OK · Medium 3.5 is NOT Apache ($20M/month revenue cap)  
  Apache 2.0: "This model is licensed under the Apache 2.0 License." (model card, which also lists "Apache 2.0 License: Open-source license for both commercial and non-commercial use"). 119B MoE released 2026. Full commercial use, fine-tuning, redistribution, self-hosting. Careful with the bigger sibling: Mistral Medium 3.5 ships under a "Modified MIT License" that says "You are not authorized to exercise any rights under this license if the global consolidated monthly revenue of your company (or that of your employer) exceeds $20 million".
- **[Qwen3.8-27B (Alibaba)](https://huggingface.co/Qwen/Qwen3.8-27B/blob/main/LICENSE)** — 🟢 Clean · Apache 2.0 · Full commercial use · No MaaS / coding-assistant exclusion (unlike Flash-Next) · Self-host OK  
  Apache 2.0 (released August 2026; LICENSE file in the Hugging Face repo) — unlike its siblings Qwen3.8-Flash-Next (Qwen Community License, no MaaS / coding-assistant business) and Qwen3.8-Max (separate licence for MaaS / AI Work Assistant businesses above US$50M revenue). Apache grants a "perpetual, worldwide, non-exclusive, no-charge, royalty-free, irrevocable copyright license": no service-type exclusion, no attribution threshold — you can build a paid coding assistant or an inference API on it. The clean pick in the Qwen3.8 family for a small commercial team.
- **[Qwen3.8-Flash-Next (Alibaba)](https://huggingface.co/Qwen/Qwen3.8-Flash-Next/blob/main/LICENSE)** — 🟡 Conditional — no MaaS / coding-assistant business · Qwen Community License 1.0 · Separate licence for API or AI-assistant businesses · Attribution above 100M MAU / $20M monthly revenue · Internal use exempt  
  Qwen Community License 1.0 (released 2026-08-24) — MIT-style grant with two conditions. First, a service-type exclusion: "If the licensee or any of its affiliates conducts a Model as a Service or AI Work Assistant business, the licensee shall obtain a separate license from Qwen before Using the Software or its derivative works for any commercial purpose." "AI Work Assistant" means a product "primarily designed for AI-assisted coding or office productivity" — so a paid coding assistant or inference API needs a deal; internal use is exempt. Second, attribution at scale: above 100M MAU or US$20M monthly revenue, the model name "must be prominently displayed on the user interface". Otherwise commercial use, fine-tuning and redistribution are allowed.

## Image Generation Models

Image-generation model weights. Mix of Apache 2.0 (commercial OK) and bespoke vendor "Community" licences with revenue caps or non-commercial clauses. The 🟢 / 🟡 pill tells you which.

- **[FLUX.2 [dev] (Black Forest Labs)](https://huggingface.co/black-forest-labs/FLUX.2-dev)** — 🟡 Conditional — non-commercial weights · FLUX [dev] Non-Commercial License · Outputs commercial OK · No training competing models on outputs · Commercial use of the model needs BFL licence · Pick klein 4B for commercial  
  FLUX [dev] Non-Commercial License (v2.0 text in BFL's flux2 repo; the gated Hugging Face card is tagged flux-non-commercial-license). The weights are non-commercial: "You may only access, use, Distribute, or create Derivatives of the FLUX [dev] Model or Derivatives for Non-Commercial Purposes." Outputs are a different story: "You may use Output for any purpose (including for commercial purposes), except as expressly prohibited herein. You may not use the Output to train, fine-tune, or distill a model that is competitive with a FLUX [dev] Model." (https://github.com/black-forest-labs/flux2/blob/main/model_licenses/LICENSE-FLUX-DEV). But "Non-Commercial Purpose" only covers use where you "do not receive any direct or indirect payment" — running it inside a paid product or for paying clients needs a BFL commercial licence. 32B flagship of the FLUX.2 family; klein 4B is the Apache 2.0 sibling.
- **[FLUX.2 [klein] 4B (Black Forest Labs)](https://huggingface.co/black-forest-labs/FLUX.2-klein-4B/blob/main/LICENSE.md)** — 🟢 Clean · Apache 2.0 · Full commercial use · Royalty-free · Sibling 9B/dev are NOT Apache (separate entries)  
  Apache 2.0: a "perpetual, worldwide, non-exclusive, no-charge, royalty-free, irrevocable copyright license". The 4B variant of FLUX.2 [klein] is released as genuinely open-source — full commercial use, modification, redistribution, royalty-free. Build a paid app, a SaaS, a game with integrated image generation — all OK. Note: the LARGER FLUX.2 [klein] 9B and FLUX.2 [dev] are NOT Apache 2.0 (see separate entries).
- **[FLUX.2 [klein] 9B (Black Forest Labs)](https://github.com/black-forest-labs/flux2/blob/main/model_licenses/LICENSE-FLUX-NON-COMMERICAL)** — 🟡 Conditional — non-commercial weights · FLUX Non-Commercial License v2.1 · Research + personal OK · Outputs commercial OK · Commercial needs BFL licence (volume tiers) · 9B capacity costs the open-source bit  
  FLUX Non-Commercial License v2.1 (the Hugging Face copy is gated; the same text is public in BFL's flux2 repo). "You may only access, use, Distribute, or create Derivatives of the FLUX Model or Derivatives for Non-Commercial Purposes." Outputs you generate may be used commercially ("You may use Output for any purpose (including for commercial purposes)"), but not to train a competing model. Shipping a paid product on the weights needs a BFL commercial licence: self-hosted licences are volume-tiered — a Builder tier (10K images/month) covers "FLUX.2 [klein] models", and the Platform tier (100K images/month) explicitly lists "FLUX.2 [klein] Base 9B + FLUX.2 [dev]" (https://bfl.ai/licensing).
- **[Qwen-Image / Qwen-Image-2512 (Alibaba)](https://github.com/QwenLM/Qwen-Image)** — 🟢 Clean · Apache 2.0 · Full commercial use · Self-host OK · Strong text-in-image rendering · Qwen-Image-2.1 is NOT Apache (separate entry)  
  Apache 2.0: "Qwen-Image is licensed under Apache 2.0." (Qwen-Image GitHub README; LICENSE file in the same repo). The newest Apache checkpoint of the text-to-image line is Qwen-Image-2512 (Hugging Face, December 2025, card tagged license: apache-2.0 — the HF repo ships no LICENSE file, the text lives on GitHub); Qwen-Image-Layered (December 2025) is also Apache. Strong open-weights text-to-image with notable strength in complex text rendering inside images. Full commercial use, modification, fine-tuning, self-hosted deployment. Note: the GitHub repo has not been updated since February 2026, and the newer Qwen-Image-2.1 (September 2026) is NOT Apache — research-only licence, see its entry.  
  <sub>★ 8.4k · last push 2026-02-10</sub>
- **[Qwen-Image-2.1 (Alibaba)](https://huggingface.co/Qwen/Qwen-Image-2.1/blob/main/LICENSE)** — 🟡 Conditional — non-commercial · Qwen Research License · Research / evaluation only · Commercial needs separate licence · Earlier Qwen-Image releases remain Apache 2.0  
  Qwen RESEARCH LICENSE AGREEMENT (release date 2026-09-20) — NOT Apache 2.0, unlike Qwen-Image and Qwen-Image-Edit. The grant is "FOR NON-COMMERCIAL PURPOSES ONLY", where "Non-Commercial" means "for research or evaluation purposes only", and "You shall not use the Materials for any commercial purpose without obtaining a separate commercial license from us." Models trained on its outputs and distributed must show "Built with Qwen" or "Improved using Qwen". Released 2026-09-14 on Hugging Face, with PE-T2I / PE-I2I variants under the same licence. For commercial image work stay on the Apache-2.0 Qwen-Image line.
- **[Qwen-Image-Edit (Alibaba)](https://github.com/QwenLM/Qwen-Image/blob/main/LICENSE)** — 🟢 Clean · Apache 2.0 · Full commercial use · Self-host OK · Natural-language image editing  
  Apache 2.0. The Hugging Face card (and the later Qwen-Image-Edit-2509 / -2511 cards) declare license: apache-2.0, but the Hugging Face repo ships no LICENSE file — the licence text lives in the Qwen-Image GitHub repo, whose README states "Qwen-Image is licensed under Apache 2.0." Alibaba's natural-language image-editing companion to Qwen-Image: full commercial use, modification, fine-tuning, self-hosted deployment. Note: the newer Qwen-Image-2.1 is NOT Apache (see its entry).
- **[Stable Diffusion 3.5 / SD3 Medium (Stability AI)](https://stability.ai/community-license-agreement)** — 🟡 Conditional — revenue cap + attribution · Stability AI Community License · <$1M revenue commercial OK · Registration required for commercial use · "Powered by Stability AI" required · Outputs are yours  
  Stability AI Community License (last updated 2024-07-05; covers SD3 Medium and SD 3.5 Large / Large Turbo / Medium). Free for research and non-commercial use, and for commercial use under a revenue cap: "If at any time You or Your Affiliate(s), either individually or in aggregate, generate more than USD $1,000,000 in annual revenue ... any licenses granted to You under this Agreement shall terminate", counted "regardless of whether that revenue is generated directly or indirectly from the Stability AI Materials or Derivative Works"; above it you need an Enterprise licence. Commercial users must register: "You must register with Stability AI." Shipping it in a product also means attribution: you must "prominently display "Powered by Stability AI" on a related website, user interface, blogpost, about page, or product documentation" and include the licence NOTICE file. Outputs: "You own any outputs generated from the Models or Derivative Works to the extent permitted by applicable law."
- **[Z-Image Turbo / Z-Image (Tongyi-MAI)](https://github.com/Tongyi-MAI/Z-Image/blob/main/LICENSE)** — 🟢 Clean · Apache 2.0 · 6B params (Turbo = fast, base = fine-tunable) · Full commercial use · Self-host OK  
  Apache 2.0 (LICENSE in the Tongyi-MAI/Z-Image GitHub repo; both Hugging Face cards tagged license: apache-2.0): a "perpetual, worldwide, non-exclusive, no-charge, royalty-free, irrevocable copyright license" to use, modify and redistribute. 6B-parameter text-to-image family from Tongyi-MAI (Alibaba). Z-Image Turbo (November 2025) is the distilled, few-step model for ultra-fast photorealistic generation; Z-Image, the full base model for fine-tuning and higher diversity, followed on 2026-01-27 under the same licence. Full commercial use, modification, redistribution, self-hosted deployment. Z-Image-Edit is announced but not yet released.

## AI Coding Assistants

IDE / desktop apps that route your code through a cloud LLM. The terms inherit from the underlying API in most cases — we link the parent entry where that's true.

- **[Claude Code / Claude Desktop](https://code.claude.com/docs/en/data-usage)** — 🟡 Conditional — depends on account type · Consumer Terms on Free / Pro / Max · Commercial Terms on Team / Enterprise / API · Training toggle on consumer plans · Local-client, cloud-inference  
  Depends on the account you sign in with. Free, Pro and Max accounts fall under Anthropic's Consumer Terms: "We will train new models using data from Free, Pro, and Max accounts when this setting is on (including when you use Claude Code from these accounts)" — retention is 5 years with the setting on, 30 days with it off. Team, Enterprise, API and cloud-platform (Bedrock, Google Cloud, Foundry) use falls under the Commercial Terms: "Anthropic does not train generative models using code or prompts sent to Claude Code under commercial terms", standard retention 30 days (https://www.anthropic.com/legal/commercial-terms). Turn the model-improvement setting off on consumer plans, or use a commercial account, before sending client code. Runs locally; prompts go to Anthropic (or your cloud provider) for inference.

## Video Generation Models

Video-generation model weights. New, fast-moving, and the licences are evolving faster than the model architectures. Always re-check the LICENCE file on the model card before you commit to a project.

- **[LTX-2.5 (Lightricks)](https://github.com/Lightricks/LTX-2/blob/main/LICENSE-2_x)** — 🟡 Conditional — multiple clauses · LTX-2.x Community License (2.5+) · Paid licence at $10M+ revenue · Keep watermark / provenance / latent disclosure · Disclose AI-generated content · No competing service · LTX-2.3 and older on LTX-2 Community License  
  LTX-2.x Community License Agreement (license date 2026-08-11), "applicable to all LTX-2.5 versions released since August 11, 2026, and all future releases of LTX-2.x under this license". Free unless you are big: "Entities with annual revenues of at least $10,000,000 (the "Commercial Entities") are required to obtain a paid license for any use (excluding use solely for a Non-Commercial Purpose as set forth in Section 2.2)", counted across affiliates; the Non-Commercial carve-out covers only personal use and testing/evaluation in a non-production environment. Unlicensed use by such an entity means "you shall pay Licensor the license fees owed for the period such Commercial Entity used LTX-2.x ... within thirty (30) days of Licensor's written demand". Conditions that apply to everyone: you "shall not remove, disable, alter, or circumvent, any safety or security measures, disclosures, metadata, watermarking, content provenance, latent disclosure, or other transparency features" (breach lets Lightricks revoke the licence immediately) and must comply with "Regulation (EU) 2024/1689 (the "EU AI Act") and the California AI Transparency Act"; Attachment A bars placing content in any context "without expressly and intelligibly disclaiming that the information and/or content is machine generated", deepfakes without consent, use in a product that "directly competes with Licensor's commercial products or services", and, "For commercial use only: To train, improve, or fine-tune any other machine learning model, artificial intelligence system, or competing model". Outputs: "Licensor claims no rights in the Output you generate using LTX-2.x." Note: the older LTX-2 through LTX-2.3 checkpoints stay under the LTX-2 Community License of 2026-01-05 (https://github.com/Lightricks/LTX-2/blob/main/LICENSE-2): same $10M line, but unlicensed use triggers liquidated damages "equal to double the amount that would otherwise have been paid".
- **[Wan 2.2 (Alibaba Tongyi Lab)](https://github.com/Wan-Video/Wan2.2)** — 🟢 Clean · Apache 2.0 · Full commercial use · Weights + code open · No vendor lock-in  
  Apache 2.0. "The models in this repository are licensed under the Apache 2.0 License. We claim no rights over the your generated contents" (Wan2.2 README; Hugging Face cards also tagged apache-2.0). Full commercial use, modification, redistribution. No revenue cap, no disclosure requirement, no anti-competition clause — the README asks that use not violate laws or cause harm. Mixture-of-experts video generation, text-to-video and image-to-video.  
  <sub>★ 17.7k · last push 2026-09-21</sub>

<!-- LIST:END -->

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
README is generated from them by [`scripts/gen_awesome_readme.py`](scripts/gen_awesome_readme.py)
— edit the YAML, not this README.

## License

[MIT](LICENSE) on the catalog itself.

The licences of the listed tools belong to their respective vendors
and are linked in each entry — read the original, not our summary,
if you're making a real decision.

---

Maintained by **[Brethof AI](https://brethof.ai)** — we read the fine print so you can ship.
