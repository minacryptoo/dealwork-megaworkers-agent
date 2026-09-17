# dealwork-megaworkers-agent
Dealwork MegaWorkers — A2A Omnitask Multi-Worker Agent
  Repositorio oficial de documentación, metadata y descubrimiento.
  Contacto: manu_shop@icloud.com
-->

# 🤖 Dealwork MegaWorkers — A2A Omnitask Multi-Worker Agent

[![A2A Protocol](https://img.shields.io/badge/A2A-0.2.9-brightgreen)](https://a2aregistry.org)
[![x402](https://img.shields.io/badge/x402-USDC%20on%20Base-blue)](https://facilitator.payai.network)
[![Uptime](https://img.shields.io/badge/uptime-24%2F7-success)](#)
[![Price](https://img.shields.io/badge/price-0.01%20USDC%2Ftask-orange)](#)
[![Workers](https://img.shields.io/badge/workers-6-purple)](#)
[![License](https://img.shields.io/badge/license-MIT-lightgrey)](./LICENSE)

> **Omnitask A2A agent: URL, archive, document, media, AI.**

**Dealwork MegaWorkers** is a production-grade **A2A (Agent-to-Agent) multi-worker agent** specialized in zero-cost file pre-processing, deterministic document and media parsing, large-scale parallel web scraping, and **Gemini AI** code generation. It exposes **6 specialized workers** (URL, archive, document, media, AI, reasoning) behind a single **JSON-RPC endpoint**, with **x402 micropayments** in **USDC on Base** via PayAI.

**Agente A2A multi-worker** de nivel producción especializado en pre-procesamiento masivo de archivos a coste cero, parsing determinista de documentos y medios, scraping web paralelo a gran escala y generación de código con **Gemini AI**. Expone **6 workers especializados** detrás de un único endpoint **JSON-RPC**, con micropagos **x402** en **USDC sobre Base** vía PayAI.

---

## 📇 Contacto

| Campo | Valor |
|-------|-------|
| **Email** | `manu_shop@icloud.com` |
| **Support / Telegram** | https://t.me/dealwork_agents |
| **Organization** | Dealwork |
| **Website** | https://dealwork.ai |
| **GitHub User** | [@minacryptoo](https://github.com/minacryptoo) |

---

## 🚀 Quick Links

| Recurso | URL |
|---------|-----|
| 🔑 **Agent Card** | https://practical-ambition-production.up.railway.app/.well-known/agent.json |
| 📋 **Skills Sitemap** | https://practical-ambition-production.up.railway.app/.well-known/skills.json |
| ⚡ **Execute Endpoint** | https://practical-ambition-production.up.railway.app/api/v1/agent/execute |
| 📊 **Task Status** | `https://practical-ambition-production.up.railway.app/api/v1/tasks/{task_id}` |
| ❌ **Task Cancel** | `https://practical-ambition-production.up.railway.app/api/v1/tasks/{task_id}/cancel` |
| 🧠 **Workers Registry** | https://practical-ambition-production.up.railway.app/api/v1/agent/workers |
| 📖 **OpenAPI** | https://practical-ambition-production.up.railway.app/openapi.json |
| 📚 **Swagger Docs** | https://practical-ambition-production.up.railway.app/docs |
| 📕 **ReDoc** | https://practical-ambition-production.up.railway.app/redoc |
| ❤️ **Health** | https://practical-ambition-production.up.railway.app/health |
| 📈 **Metrics** | https://practical-ambition-production.up.railway.app/metrics |
| 🤖 **Robots** | https://practical-ambition-production.up.railway.app/robots.txt |

---

## 🔑 Identidad del Agente / Agent Identity

```

Agent Name:        Dealwork-MegaWorkers
Agent Version:     2.0.0
Agent ID:          did:web:dealwork.ai:megaworkers
Agent URL:         https://practical-ambition-production.up.railway.app
Protocol Version:  0.2.9
Transport:         JSONRPC
Category:          developer_tools_and_data_processing
Languages:         en, es

```

---

## 🧠 Skills / Workers (6)

### 1. `url_worker` — Bulk URL Checker & Scraper
Verificación y scraping paralelo de hasta **5.000 URLs por tarea** (status, title, OG tags, metadata SEO).
**Tags:** `url`, `scraper`, `bulk`, `http`, `metadata`, `seo`

### 2. `archive_worker` — Archive Decompression & Tree Inspection
Descompresión y análisis de **ZIP/TAR/GZ/7Z/RAR** hasta **200 MB**, extracción de árboles de directorios.
**Tags:** `zip`, `tar`, `archive`, `decompress`, `tree`

### 3. `document_worker` — Document & Code Parsing
Conversión determinista **PDF→Markdown/TXT, JSON↔CSV, YAML, DOCX** (hasta 50 MB) a coste cero.
**Tags:** `pdf`, `markdown`, `json`, `csv`, `yaml`, `docx`, `conversion`

### 4. `media_worker` — FFmpeg Media Transcoding & Audio Extraction
**FFmpeg completo**: extracción de audio, trim, transcoding de **+25 formatos** (MP4/MP3/WAV/MKV…) hasta **500 MB**.
**Tags:** `ffmpeg`, `audio`, `video`, `transcode`, `mp3`, `mp4`

### 5. `ai_worker` — Gemini AI Text/Code Generation
Generación de texto, código, investigación, traducción y razonamiento complejo con **Gemini AI**.
**Tags:** `gemini`, `llm`, `writing`, `research`, `code`, `translation`

### 6. `gemini_generalist_worker` — Gemini Generalist / Reasoning Fallback
Fallback inteligente para razonamiento abstracto, lógica personalizada y ejecución de código.
**Tags:** `reasoning`, `fallback`, `custom_logic`

---

## 🎯 Lista Compacta de Capacidades

```

url-checker, web-scraper, pdf-parser, document-converter,
archive-extractor, ffmpeg-transcoder, media-processor,
ai-generation, code-review, translation, research,
data-analysis, content-generation, rag-preprocessing,
a2a-agent, x402-merchant, multi-worker, omnitask-agent,
python-sandbox, presentation-generator, book-writer,
bot-builder, website-generator, apk-code-generator

```

---

## 💰 Pricing / Precios

| Concepto | Valor |
|----------|-------|
| **Modelo** | Pay-per-task (x402) |
| **Precio por tarea** | **0.01 USDC** |
| **Red principal** | Base (eip155:8453) |
| **Redes soportadas** | Base, Polygon, Arbitrum, Optimism, Ethereum, Solana |
| **Asset preferido** | USDC |
| **Facilitator** | https://facilitator.payai.network |
| **x402 Version** | 1 |
| **Free tier** | 5 tasks/día, máx 5 MB por tarea |

### Bulk Tiers (volumen)

| Tier | Unidades | Descuento | Precio/tarea |
|------|----------|-----------|--------------|
| Pay as you go | 1 – 99 | 0% | 0.01 USDC |
| Starter Pack | 100 – 999 | 10% | 0.009 USDC |
| Growth Pack | 1.000 – 9.999 | 25% | 0.0075 USDC |
| Pro Volume | 10.000 – 99.999 | 40% | 0.006 USDC |
| Enterprise Bulk | 100.000 – 999.999 | 50% | 0.005 USDC |
| Mega Scale | 1.000.000+ | 60% | 0.004 USDC |

### Wallets de cobro (públicas)

```

EVM Wallet:     0xdE732Ef88Eabd42e6510a38c2D191B74FD566C0B
Solana Wallet:  EKf6HPb72XWeKzBCdpo2dy25mW325rSkNg2a89RFG34z

```

### USDC Contract Addresses

| Red | Dirección |
|-----|-----------|
| Base | `0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913` |
| Ethereum | `0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48` |
| Polygon | `0x3c499c542cEF5E3811e1192ce70d8cC03d5c3359` |
| Arbitrum | `0xaf88d065e77c8cC2239327C5EDb3A432268e5831` |
| Optimism | `0x0b2C639c533813f4Aa9D7837CAf62653d097Ff85` |
| Solana | `EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v` |

---

## ⚙️ Especificaciones Técnicas

| Parámetro | Valor |
|-----------|-------|
| Workers | 6 |
| Thread Model | daemon-threads |
| Uptime Target | 24/7 |
| Rate Limit | 120 RPM global |
| Max Concurrent | 10 tareas |
| Max Timeout | 300s |
| Streaming | No |
| Push Notifications | Sí |
| State History | Sí |
| SLA Availability | 99.5% |
| P95 Latency | 8s |

### Límites por Skill

| Worker | Límite |
|--------|--------|
| `url_worker` | 5.000 URLs/task, 300s, 60 RPM |
| `archive_worker` | 200 MB, 120s |
| `document_worker` | 50 MB, 60s |
| `media_worker` | 500 MB, 300s, 2 concurrent |
| `ai_worker` | 200K chars, 120s, 60 RPM |
| `gemini_generalist_worker` | 100K chars, 120s, 30 RPM |

---

## 🔍 SEO & Discovery

### Keywords

```

pdf-to-markdown, pdf-extractor, audio-extractor, ffmpeg-transcoder,
python-execution, code-sandbox, web-scraper, bulk-url-checker,
csv-to-json, zip-extractor, ai-researcher, data-parser,
media-processing, gemini-ai, token-optimization, a2a-agent,
omnitask-agent, multi-worker, x402-merchant, payai,
a2a, mcp, mcp-server, autonomous-agent, developer-tools,
data-processing, document-parser, media-transcoder,
ai-code-generation, rag-preprocessing, presentation-generator,
book-writer, bot-builder, website-generator, apk-code-generator

```

### Intents

```

convert_document, extract_audio, transcode_media, run_python_code,
scrape_urls, analyze_data, unzip_archive, generate_content,
research_topic, bulk_url_check, translate_text, review_code

```

### Use Cases

- Bulk URL validation for SEO audits
- PDF→Markdown conversion for RAG pipelines
- Media preprocessing to reduce LLM token cost
- Automated research memos with citations
- Pay-per-task x402 micropayments via PayAI
- Bot source-code generation (Telegram, Discord, WhatsApp, X)
- Ready-to-deploy website generation
- Ebook / presentation / documentation generation
- APK source code generation and review
- Multi-language translation at scale

### Especialidades (SEO ES)

```

web-scraper, bulk-url-checker, pdf-to-markdown, document-converter,
archive-extractor, ffmpeg-transcoder, media-processor, audio-extractor,
ai-code-generation, code-review, translation, research-agent,
data-analysis, content-generation, rag-preprocessing, a2a-agent,
x402-merchant, multi-worker, omnitask-agent, python-sandbox,
presentation-generator, book-writer, bot-builder, website-generator,
apk-code-generator

```

---

## 🌍 Descripción Multilingüe

### 🇪🇸 Español

**Agente A2A autónomo multi-worker** de alto rendimiento especializado en **pre-procesamiento masivo de archivos a coste cero**, **parsing determinista de documentos y medios**, **scraping web paralelo a gran escala**, **generación de código**, **creación de contenido estructurado** y **ejecución de tareas complejas con Gemini AI**. Ideal para **pipelines RAG**, **automatización industrial de datos**, **generación de activos digitales** y **ejecución de miles de tareas concurrentes 24/7**.

### 🇬🇧 English

**Autonomous multi-worker A2A agent** specialized in **zero-cost mass file pre-processing**, **deterministic document & media parsing**, **large-scale parallel web scraping**, **code generation**, **structured content creation**, and **complex task execution powered by Gemini AI**. Built for **RAG pipelines**, **industrial data automation**, **digital asset generation**, and **high-volume concurrent task execution 24/7**.

---

## 🧪 Ejemplos de Uso / Usage Examples

### Verificar 500 URLs
```bash
curl -X POST https://practical-ambition-production.up.railway.app/api/v1/agent/execute \
  -H "Content-Type: application/json" \
  -H "X-PAYMENT: <x402-receipt>" \
  -d '{
    "skill": "url_worker",
    "input": { "urls": ["https://example.com", "..."] }
  }'
```

Convertir PDF a Markdown

```bash
curl -X POST https://practical-ambition-production.up.railway.app/api/v1/agent/execute \
  -H "Content-Type: multipart/form-data" \
  -F "skill=document_worker" \
  -F "file=@documento.pdf"
```

Extraer audio de un vídeo (FFmpeg)

```bash
curl -X POST https://practical-ambition-production.up.railway.app/api/v1/agent/execute \
  -H "Content-Type: multipart/form-data" \
  -F "skill=media_worker" \
  -F "file=@video.mp4" \
  -F "operation=extract_audio"
```

---

🗂️ Verificación y Registros Públicos

Registro URL
A2A Registry https://a2aregistry.org/agents
x402 Bazaar https://facilitator.payai.network/discovery/resources
Coinbase CDP https://api.cdp.coinbase.com/platform/v2/x402/discovery/merchant?payTo=0xdE732Ef88Eabd42e6510a38c2D191B74FD566C0B
PayAI Bazaar https://facilitator.payai.network/discovery/resources
Agentic.Market https://agentic.market

---

🔐 Seguridad / Security

Este repositorio es público y NO contiene secretos. Las siguientes variables se gestionan exclusivamente como variables de entorno en Railway:

· GPT_API_KEY
· SUPABASE_ANON_KEY
· AGENT_API_KEY
· APP_API_KEY

Nunca se subirán al repositorio. Consulta el .gitignore para más detalles.

---

📜 Licencia / License

MIT License — ver LICENSE para más detalles.

---

🤝 Contribuir / Contributing

¿Quieres integrar Dealwork MegaWorkers en tu plataforma A2A o en tu pipeline? Abre un issue o contacta directamente:

📧 manu_shop@icloud.com

---

🌟 Star History

Si este agente te resulta útil, considera darle una ⭐ al repositorio. Ayuda a la visibilidad y al descubrimiento en el ecosistema A2A.

---

<!-- SEO Footer: A2A agent, MCP server, multi-worker, web scraper, PDF to Markdown, FFmpeg transcoder, Gemini AI, x402, USDC, Base, PayAI, autonomous agent, developer tools, data processing, RAG pipeline, document parser, media processor, AI code generation, omnitask agent, pay-per-task agent -->
