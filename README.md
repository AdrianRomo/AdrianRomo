# Adrian Romo

Senior backend engineer in Mexico City (UTC-6). 9+ years in Python.

I build the layer between a product and everything it has to talk to: chat platforms, phone lines, speech models, LLMs, and the infrastructure underneath. Lately that means voice agents and agent tooling.

I work in English and Spanish, and I'm open to senior backend, platform and voice AI roles, remote.

[Website](https://adrianromo.me) · [Case studies](https://adrianromo.me/projects) · [Blog](https://adrianromo.me/blog) · [Resume](https://adrianromo.me/resume) · [LinkedIn](https://www.linkedin.com/in/adrianromo97)

---

## Work I'm proud of

### Four chat channels and a phone line behind one interface · Resolve Systems

[Case study](https://adrianromo.me/projects/omni-router)

I designed the Factory Method integration layer our virtual support agent runs on. Slack, Microsoft Teams, Google Chat and Webex sit behind one interface, and that interface says nothing about when a reply arrives. So when we needed a phone line, a blocking call became one more adapter.

I moved the existing integrations onto it while they kept running in production, and each new chat channel turned into a quick plug-in. The customer-facing APIs on top held at **zero critical vulnerabilities for 2 years**.

### Voice agents · Resolve Systems

[Case study](https://adrianromo.me/projects/voice-orchestrator)

I designed and built the original IVR agent on Amazon Connect, Lex, Lambda and Polly. The async chatbot backend was shared production infrastructure, so forking it for voice was off the table. I bridged the call into it.

I led the voice integration, including the provider and cost decisions. Later the channel moved to a Vapi agent and fulfillment logic didn't change at all. The platform as a whole helped cut help-desk call volume by **40-60%**.

### Realtime voice agent · personal

A Pipecat pipeline (streaming speech-to-text, LLM, speech synthesis) with Silero VAD, semantic turn endpointing, barge-in, and per-utterance language detection, so it answers in the language you spoke.

Splitting latency by stage showed turn detection is the critical path. And a tool-grounded turn costs a second model round trip (0.64s vs 0.17s to first token), while the tool itself runs in 0.04s.

### Agent tooling for my homelab · personal

[Ops case study](https://adrianromo.me/projects/homelab-ops) · [Second Brain case study](https://adrianromo.me/projects/homelab-second-brain)

- An MCP server with 90+ read-only tools over live infrastructure. Read-only is enforced in the tool schemas, a container socket proxy that rejects writes, and argument filtering below the model.
- A write loop: detect, propose, human approve, act. Approved work lands as a draft pull request, and conclusions without evidence get blocked.
- A compiled memory layer for local models: **~99% fewer tokens per query** (30-50K down to 2-5K), validated in shadow mode against the old RAG path before it took over. Answers carry citations.
- Built with Claude Code and Codex as coding agents while I own architecture, review, security and testing: 308 merged PRs from June to November 2026. It runs every day across 11 hosts and 176 containers.

### Smaller things

- [Influencer-Automation](https://github.com/AdrianRomo/Influencer-Automation): turns RSS news into audio and video with the ElevenLabs and OpenAI APIs.
- [Grocery Cart Bridge](https://adrianromo.me/projects/grocery-cart-bridge): turns a meal-planner list into a cart proposal for a human to review, and stops before buying anything. Python, MCP, pytest.
- [This portfolio](https://adrianromo.me/projects/this-portfolio): multilingual Next.js site with a retrieval assistant (pgvector, OpenAI), a translation pipeline, and a generated PDF resume.
- [Short-form video pipeline](https://adrianromo.me/projects/short-form-video-pipeline): my deployment of an open-source video generator, with about 57 commits of my own on top of upstream. Runs on CUDA at home and CPU-only as a public demo.

Most of my professional work lives in private repos. The case studies are the long version.

---

## Writing

- [Building Voice Integrations on Top of Async Chatbots](https://adrianromo.me/blog/voice-integrations-on-top-of-async-chatbots)
- [Assembled Primitives vs. a Platform](https://adrianromo.me/blog/assembled-primitives-vs-a-platform): why the voice channel moved from AWS primitives to Vapi
- [What I Learned Designing Omnichannel Backend Integrations](https://adrianromo.me/blog/omnichannel-backend-integrations-lessons)
- [A Write Loop That Never Merges Anything](https://adrianromo.me/blog/gated-write-loop)
- [A Second Brain That Refuses to Guess](https://adrianromo.me/blog/compiled-memory-layer-for-local-models)
- [The Alert That Named a Thing and Called It Evidence](https://adrianromo.me/blog/evidence-vs-naming)

---

## How I work

- I design the seam first, so the later migration is cheap. Our voice channel went from an IVR to Vapi and fulfillment never noticed.
- I put safety in the structure: schemas, proxies and filters below the model.
- I write it down. Case studies, ADRs, runbooks and postmortems are how I hand work off.

---

## Stack

**Backend:** Python, Django (7+ years), FastAPI, Flask, Celery, REST APIs, Postgres, Redis

**Voice & AI:** Pipecat, Vapi, Amazon Connect, Lex, Polly, Deepgram, Whisper, MCP, Qdrant, pgvector, Ollama, Claude Code, Codex

**Cloud & infra:** AWS Lambda, S3, IAM, Docker, Kubernetes, Terraform, Traefik, Prometheus, Grafana, Loki, Proxmox

**Frontend (this portfolio):** Next.js, TypeScript, Tailwind, Prisma

---

**Get in touch:** [adrian.romo.dev@gmail.com](mailto:adrian.romo.dev@gmail.com) · [LinkedIn](https://www.linkedin.com/in/adrianromo97) · [adrianromo.me](https://adrianromo.me)
