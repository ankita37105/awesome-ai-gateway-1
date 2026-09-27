# Awesome AIgateway [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of integrations, agents, frameworks, examples, and community projects built on [**AIgateway**](https://aigateway.sh) — one OpenAI-compatible endpoint to 150+ AI models across 44 labs.

Contributions welcome — see [Contributing](#contributing) below.

## Contents

- [What is AIgateway](#what-is-aigateway)
- [Official packages](#official-packages)
- [Coding agents](#coding-agents)
- [Agent frameworks](#agent-frameworks)
- [Web frameworks & UI](#web-frameworks--ui)
- [Eval, gateway, and ops tools](#eval-gateway-and-ops-tools)
- [Workflow & automation](#workflow--automation)
- [Deploy targets](#deploy-targets)
- [Examples & starters](#examples--starters)
- [Videos & tutorials](#videos--tutorials)
- [Community projects](#community-projects)
- [Contributing](#contributing)

## What is AIgateway

A single API that gives you 150+ models behind one key — Anthropic, OpenAI, Google, Moonshot, Meta, Mistral, DeepSeek, Black Forest Labs, Stability, Deepgram, ElevenLabs, Runway, and more. OpenAI-compatible, cost + 5%, failover built in. [Get a key →](https://aigateway.sh/signin)

## Official packages

- [**aigateway-cli**](https://www.npmjs.com/package/aigateway-cli) — `aig` command-line tool: call any model, mint keys, run evals, tail traffic. [source](https://github.com/aigateway-sh/cli)
- [**aigateway-js**](https://www.npmjs.com/package/aigateway-js) — TypeScript/Node SDK. [source](https://github.com/aigateway-sh/sdk-node)
- [**aigateway-py**](https://pypi.org/project/aigateway-py/) — Python SDK. [source](https://github.com/aigateway-sh/sdk-python)
- [**openapi**](https://github.com/aigateway-sh/openapi) — OpenAPI 3.1 spec for generating clients in any language.
- [**mcp-server**](https://github.com/aigateway-sh/mcp-server) — Reference MCP server; hosted at `api.aigateway.sh/mcp`.
- [**llms-txt**](https://github.com/aigateway-sh/llms-txt) — Capability map agents can self-configure against.
- [**examples**](https://github.com/aigateway-sh/examples) — Chat, embeddings, image, voice, multimodal agents.

## Coding agents

Drop-in OpenAI-compatible — point the base URL at `https://api.aigateway.sh/v1` and most agents "just work".

- [**Claude Code**](https://claude.com/product/claude-code) — add via `claude mcp add`. See [mcp-server docs](https://github.com/aigateway-sh/mcp-server#claude-code).
- [**Cursor**](https://cursor.com) — override OpenAI base URL in `Cursor Settings → AI → Custom OpenAI Base URL`.
- [**Cline**](https://github.com/cline/cline) — OpenAI-compatible provider with custom base URL.
- [**Aider**](https://aider.chat) — `aider --openai-api-base https://api.aigateway.sh/v1 --openai-api-key sk-aig-...`
- [**Continue.dev**](https://continue.dev) — JetBrains/VS Code IDE agent, supports OpenAI-compatible providers.
- [**OpenClaw**](https://github.com/openclaw-ai/openclaw) — Claude alternative, fully MCP-first, pairs well with our MCP server.
- [**Codex CLI**](https://github.com/openai/codex) — set `OPENAI_BASE_URL`.
- [**Zed**](https://zed.dev) — supports OpenAI-compatible providers in assistant config.

## Agent frameworks

- [**Mastra**](https://mastra.ai) — TypeScript agent framework; configure the OpenAI provider with our base URL.
- [**LangChain (JS/Python)**](https://www.langchain.com) — `ChatOpenAI(base_url=...)` or `new ChatOpenAI({ baseURL: ... })`.
- [**LlamaIndex**](https://www.llamaindex.ai) — works via OpenAI-compatible provider.
- [**Vercel AI SDK**](https://sdk.vercel.ai) — `createOpenAI({ baseURL: "https://api.aigateway.sh/v1" })`.
- [**CrewAI**](https://www.crewai.com) — set `OPENAI_API_BASE`.
- [**AutoGen**](https://microsoft.github.io/autogen/) — configure `config_list` with our base URL.
- [**Haystack**](https://haystack.deepset.ai) — OpenAI-compatible generator with custom `api_base_url`.

## Web frameworks & UI

- [**Next.js + Vercel AI SDK**](https://github.com/vercel/ai) — see [`examples/chat`](https://github.com/aigateway-sh/examples/tree/main/chat).
- [**Remix / Hono / Express / Fastify**](https://hono.dev) — any Node framework works with `aigateway-js`.
- [**Chainlit**](https://chainlit.io) — Python chat UI; swap the base URL.
- [**Streamlit**](https://streamlit.io) — pair with `aigateway-py`.
- [**Gradio**](https://gradio.app) — same.
- [**shadcn/ui chat templates**](https://ui.shadcn.com) — works out of the box.

## Eval, gateway, and ops tools

- [**Promptfoo**](https://promptfoo.dev) — `providers: ['openai:chat:anthropic/claude-opus-4.7']` with `apiBaseUrl: https://api.aigateway.sh/v1`.
- [**LiteLLM**](https://github.com/BerriAI/litellm) — add AIgateway as a custom provider; useful for teams already on LiteLLM.
- [**Langfuse**](https://langfuse.com) — OpenAI-wrapper auto-instruments; points traces at AIgateway transparently.
- [**Helicone**](https://www.helicone.ai) — same — proxy or OpenAI wrapper approach.
- [**OpenPipe**](https://openpipe.ai) — fine-tuning and eval; uses OpenAI-compatible base URL.
- [**Pezzo**](https://pezzo.ai) — prompt management, OpenAI-compatible.

## Workflow & automation

- [**n8n**](https://n8n.io) — HTTP Request node or OpenAI node with custom URL. See [aigateway.sh/integrations/n8n](https://aigateway.sh/integrations/n8n).
- [**Zapier / Make / Pipedream**](https://zapier.com) — use the OpenAI integration with `api.aigateway.sh/v1`.
- [**Temporal**](https://temporal.io) — orchestrate async `create_job` calls with retries/timeouts.
- [**Inngest**](https://www.inngest.com) — background jobs that call AIgateway.
- [**Trigger.dev**](https://trigger.dev) — same.

## Deploy targets

- [**Cloudflare Workers**](https://workers.cloudflare.com) — `aigateway-js` runs in Workers out of the box.
- [**Vercel**](https://vercel.com) — one-click deploy buttons on every example in [examples](https://github.com/aigateway-sh/examples).
- [**Fly.io**](https://fly.io) — Dockerize anything that uses `aigateway-py` or `aigateway-js`.
- [**Railway / Render / AWS Lambda / GCP Cloud Run**](https://railway.app) — no provider-specific runtime requirements.
- [**Netlify Functions**](https://www.netlify.com) — works with `aigateway-js`.

## Examples & starters

Everything in [`examples/`](https://github.com/aigateway-sh/examples) is runnable in <60 seconds and deploys to Vercel with one click:

- [**chat**](https://github.com/aigateway-sh/examples/tree/main/chat) — streaming chat UI, Next.js + shadcn/ui.
- [**embeddings**](https://github.com/aigateway-sh/examples/tree/main/embeddings) — RAG quickstart with pgvector or Turbopuffer.
- [**image**](https://github.com/aigateway-sh/examples/tree/main/image) — FLUX / Ideogram / SDXL from one surface.
- [**voice**](https://github.com/aigateway-sh/examples/tree/main/voice) — STT → LLM → TTS pipeline.
- [**multimodal-agent**](https://github.com/aigateway-sh/examples/tree/main/multimodal-agent) — a Python agent that reasons across image, text, and audio.

## Videos & tutorials

_Nothing yet — be the first! Send a PR._

## Community projects

_Nothing yet — open a PR to add yours._ We highlight projects that are MIT/Apache-licensed, genuinely useful, and have at least basic docs

- [APIClaw](https://apiclaw.biz)  Flat-rate OpenAI-compatible AI API gateway for Claude, GPT, Kimi, Qwen, DeepSeek, and GLM..

## Contributing

1. Open a pull request with your addition.
2. Keep the description to **one line** — "What it is, why a dev would care."
3. Link to source (preferably open-source, but commercial products with docs are fine).
4. Add it under the most specific category. When in doubt, ask in [discussions](https://github.com/aigateway-sh/awesome-ai-gateway/discussions).

See [`CONTRIBUTING.md`](./CONTRIBUTING.md) for the full criteria.

## License

[CC0-1.0](./LICENSE) — this list is public domain. Copy, remix, fork freely.
