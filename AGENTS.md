<!--
  ═══════════════════════════════════════════════════════════════════════════
  DEALWORK MEGAWORKERS — A2A OMNIWORKER AGENT
  ═══════════════════════════════════════════════════════════════════════════
  Agent ID:        did:web:dealwork.ai:megaworkers
  Version:         2.0.0
  Protocol:        A2A (JSON-RPC) 0.2.9
  Repository:      dealwork-megaworkers-agent
  Contact:         manu_shop@icloud.com
  License:         MIT
  ═══════════════════════════════════════════════════════════════════════════
  SEO KEYWORDS: a2a agent, mcp server, multi-worker agent, web scraper,
  bulk url checker, pdf to markdown, ffmpeg transcoder, gemini ai agent,
  x402 merchant, usdc base, payai, autonomous agent, developer tools,
  data processing, rag pipeline, document parser, media processor,
  python sandbox, code generation, bot builder, website generator,
  apk code generator, book writer, presentation generator, omnitask agent
  ═══════════════════════════════════════════════════════════════════════════
-->

# 🤖 Dealwork MegaWorkers

## `did:web:dealwork.ai:megaworkers` — v2.0.0 — A2A Multi-Worker Agent

[![A2A Protocol](https://img.shields.io/badge/A2A-0.2.9-brightgreen)](https://a2aregistry.org)
[![x402](https://img.shields.io/badge/x402-USDC%20on%20Base-blue)](https://facilitator.payai.network)
[![Workers](https://img.shields.io/badge/workers-6-purple)](#-skills--workers)
[![Price](https://img.shields.io/badge/price-0.01%20USDC%2Ftask-orange)](#-pricing)
[![Uptime](https://img.shields.io/badge/uptime-24%2F7-success)](#)
[![License](https://img.shields.io/badge/license-MIT-lightgrey)](./LICENSE)

> **Omnitask A2A agent: URL, archive, document, media, AI.**

**Dealwork MegaWorkers** is a production-grade **A2A (Agent-to-Agent) multi-worker agent** specialized in zero-cost file pre-processing, deterministic document and media parsing, large-scale parallel web scraping, and **Gemini AI** code generation. It exposes **6 specialized workers** behind a single **JSON-RPC endpoint**, with **x402 micropayments** in **USDC on Base** via PayAI.

**Dealwork MegaWorkers** es un **agente A2A multi-worker** de nivel producción especializado en pre-procesamiento masivo de archivos a coste cero, parsing determinista de documentos y medios, scraping web paralelo a gran escala y generación de código con **Gemini AI**. Expone **6 workers especializados** detrás de un único endpoint **JSON-RPC**, con micropagos **x402** en **USDC sobre Base** vía PayAI.

---

## 📇 Contact

| Field | Value |
|-------|-------|
| **Primary Email** | `manu_shop@icloud.com` |
| **GitHub User** | [@minacryptoo](https://github.com/minacryptoo) |

---

## 🔑 Agent Identity

```yaml
Agent Name:        Dealwork-MegaWorkers
Agent Version:     2.0.0
Agent ID:          did:web:dealwork.ai:megaworkers
Agent URL:         https://practical-ambition-production.up.railway.app
Protocol Version:  0.2.9
Transport:         JSONRPC
Preferred Transport: JSONRPC
Category:          developer_tools_and_data_processing
Languages:         en, es
Icon:              https://dealwork.ai/static/icon.png
```

---

🌐 Endpoints

Endpoint URL Method
Agent Card https://practical-ambition-production.up.railway.app/.well-known/agent.json GET
Skills Sitemap https://practical-ambition-production.up.railway.app/.well-known/skills.json GET
Execute https://practical-ambition-production.up.railway.app/api/v1/agent/execute POST
Task Status https://practical-ambition-production.up.railway.app/api/v1/tasks/{task_id} GET
Task Cancel https://practical-ambition-production.up.railway.app/api/v1/tasks/{task_id}/cancel POST
Workers Registry https://practical-ambition-production.up.railway.app/api/v1/agent/workers GET
Health https://practical-ambition-production.up.railway.app/health GET
Metrics https://practical-ambition-production.up.railway.app/metrics GET
OpenAPI https://practical-ambition-production.up.railway.app/openapi.json GET
Swagger Docs https://practical-ambition-production.up.railway.app/docs GET
ReDoc https://practical-ambition-production.up.railway.app/redoc GET
Robots https://practical-ambition-production.up.railway.app/robots.txt GET
x402 Supported https://facilitator.payai.network/supported GET
x402 Bazaar https://facilitator.payai.network/discovery/resources GET

---

🧠 Skills / Workers

1. url_worker — Bulk URL Checker & Scraper

Priority: 10

Parallel status/title/OG metadata extraction across large URL lists.

Capacidades:

· Check status codes for 500 URLs
· Extract titles and OG tags from a domain list
· Bulk verify link availability
· SEO metadata extraction (title, description, OG tags, canonical)
· Parallel processing (hasta 5.000 URLs por tarea)

Tags: url scraper bulk http metadata seo

Input Modes: application/json text/plain
Output Modes: application/json

Límites:

```yaml
max_urls_per_task: 5000
timeout: 300s
rpm: 60
```

Combinaciones de archivos aceptadas:

```
.txt, .json, .csv, .md  →  .json
```

---

2. archive_worker — Archive Decompression & Tree Inspection

Priority: 15

Zip/tar/gz/tgz/bz2/xz/7z/rar decompression, compression and directory tree extraction with zero token overhead.

Capacidades:

· Extract this ZIP and list its tree
· Compress these files into tar.gz
· Inspect paths inside an archive
· Directory tree extraction
· Zero token overhead processing

Tags: zip tar archive decompress tree

Input Modes: application/zip application/x-tar application/gzip application/json
Output Modes: application/json

Límites:

```yaml
max_file_size_mb: 200
timeout: 120s
```

Combinaciones de archivos aceptadas:

```
.zip, .tar, .gz, .tgz, .bz2, .xz, .7z, .rar  →  .json
```

---

3. document_worker — Document & Code Parsing

Priority: 20

PDF→MD/TXT, JSON↔CSV, YAML, DOCX metadata extraction. Deterministic, $0 tokens.

Capacidades:

· Convert this PDF to markdown
· Turn this JSON array into CSV
· Extract text from a scanned PDF
· Convert JSON ↔ CSV ↔ YAML ↔ Markdown
· DOCX metadata extraction
· Deterministic parsing (zero LLM tokens)

Tags: pdf markdown json csv yaml docx conversion

Input Modes: application/pdf text/markdown application/json text/csv application/x-yaml
Output Modes: text/markdown application/json text/csv

Límites:

```yaml
max_file_size_mb: 50
timeout: 60s
```

Combinaciones de archivos aceptadas:

```
.pdf, .md, .txt, .json, .csv, .yaml, .yml, .docx, .doc  →  .md, .json, .csv, .txt
```

---

4. media_worker — FFmpeg Media Transcoding & Audio Extraction

Priority: 25

Extract audio, trim clips, transcode MP4/MP3/WAV/MKV and 25+ formats via FFmpeg.

Capacidades:

· Extract MP3 audio from this MP4
· Trim first 30s of a video
· Transcode MKV to MP4
· Extract audio (MP3/WAV/AAC/FLAC/OGG)
· Video trimming y conversión entre +25 formatos
· Audio preprocessing para reducir costes LLM

Tags: ffmpeg audio video transcode mp3 mp4

Input Modes: video/mp4 video/x-matroska audio/mpeg audio/wav application/json
Output Modes: audio/mpeg video/mp4 application/json

Límites:

```yaml
max_file_size_mb: 500
timeout: 300s
concurrent: 2
```

Combinaciones de archivos aceptadas:

```
Entrada: .mp4, .mkv, .avi, .mov, .webm, .flv, .wmv, .mp3, .wav, .aac, .flac, .ogg, .m4a, .opus, .wma, .aiff
Salida:  .mp4, .mp3, .wav, .aac, .flac, .ogg, .mkv, .webm, .json
```

---

5. ai_worker — Gemini AI Text/Code Generation

Priority: 50

Auto-discovered Gemini models with cascading fallback for writing, research, code review and translation.

Capacidades:

· Write a 500-word article about X
· Review this Python code and suggest improvements
· Translate this text to English
· Content generation (blogs, ebooks, documentation)
· Code generation and review
· Research and summarization
· Multi-language translation

Tags: gemini llm writing research code translation

Input Modes: text/plain application/json
Output Modes: text/markdown application/json

Límites:

```yaml
max_input_chars: 200000
timeout: 120s
rpm: 60
```

Combinaciones de archivos aceptadas:

```
.txt, .md, .json, .pdf, .csv, .yaml  →  .md, .json, .txt
```

---

6. gemini_generalist_worker — Gemini Generalist / Reasoning Fallback

Priority: 90

Fallback for abstract reasoning, custom logic and code_execution tasks not covered by specialized workers.

Capacidades:

· Solve this multi-step logic problem
· Design a workflow for X
· Custom logic generation
· Multi-step reasoning
· Python code execution sandbox
· Fallback inteligente para tareas no cubiertas

Tags: reasoning fallback custom_logic

Input Modes: text/plain application/json
Output Modes: text/markdown application/json

Límites:

```yaml
max_input_chars: 100000
timeout: 120s
rpm: 30
```

Combinaciones de archivos aceptadas:

```
.txt, .md, .json, .py  →  .md, .json, .txt
```

---

📊 Matriz Completa de Combinaciones de Archivos

Worker Entrada Salida
url_worker .txt, .json, .csv, .md .json
archive_worker .zip, .tar, .gz, .tgz, .bz2, .xz, .7z, .rar .json
document_worker .pdf, .md, .txt, .json, .csv, .yaml, .yml, .docx, .doc .md, .json, .csv, .txt
media_worker .mp4, .mkv, .avi, .mov, .webm, .flv, .wmv, .mp3, .wav, .aac, .flac, .ogg, .m4a, .opus, .wma, .aiff .mp4, .mp3, .wav, .aac, .flac, .ogg, .mkv, .webm, .json
ai_worker .txt, .md, .json, .pdf, .csv, .yaml .md, .json, .txt
gemini_generalist_worker .txt, .md, .json, .py .md, .json, .txt

---

🎯 Lista Compacta de Capacidades (una línea)

```
url-checker, web-scraper, bulk-url-checker, pdf-parser, pdf-to-markdown,
document-converter, json-to-csv, csv-to-json, yaml-parser, docx-parser,
archive-extractor, zip-extractor, tar-extractor, ffmpeg-transcoder,
media-processor, audio-extractor, video-transcoder, ai-generation,
code-review, code-generation, translation, research, data-analysis,
content-generation, rag-preprocessing, a2a-agent, x402-merchant,
multi-worker, omnitask-agent, python-sandbox, presentation-generator,
book-writer, bot-builder, website-generator, apk-code-generator
```

---

💰 Pricing

Concepto Valor
Modelo Pay-per-task (x402)
Precio base por tarea 0.01 USDC
Precio por archivo 0.005 USDC
Precio por MB 0.001 USDC
Cargo mínimo 0.01 USDC
Moneda USDC
Red principal Base (eip155:8453)
Redes soportadas Base, Polygon, Arbitrum, Optimism, Ethereum, Solana
Facilitator https://facilitator.payai.network
x402 Version 1
Free Tier 5 tareas/día, máx 5 MB por tarea

Fórmula: per_task + (per_file * n_files) + (per_mb * ceil(total_mb))

Bulk Tiers

Tier Unidades Descuento Precio/tarea Precio/1K
Pay as you go 1 – 99 0% 0.01 USDC 10.0 USDC
Starter Pack 100 – 999 10% 0.009 USDC 9.0 USDC
Growth Pack 1.000 – 9.999 25% 0.0075 USDC 7.5 USDC
Pro Volume 10.000 – 99.999 40% 0.006 USDC 6.0 USDC
Enterprise Bulk 100.000 – 999.999 50% 0.005 USDC 5.0 USDC
Mega Scale 1.000.000+ 60% 0.004 USDC 4.0 USDC

Wallets de cobro (públicas)

```
EVM Wallet:     0xdE732Ef88Eabd42e6510a38c2D191B74FD566C0B
Solana Wallet:  EKf6HPb72XWeKzBCdpo2dy25mW325rSkNg2a89RFG34z
```

USDC Contract Addresses

Red Dirección
Base 0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913
Ethereum 0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48
Polygon 0x3c499c542cEF5E3811e1192ce70d8cC03d5c3359
Arbitrum 0xaf88d065e77c8cC2239327C5EDb3A432268e5831
Optimism 0x0b2C639c533813f4Aa9D7837CAf62653d097Ff85
Solana EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v

---

⚙️ Technical Specs

Parámetro Valor
Workers 6
Thread Model daemon-threads
Uptime Target 24/7
Rate Limit 120 RPM global
Max Concurrent 10 tasks
Max Timeout 300s
Streaming No
Push Notifications Yes
State Transition History Yes
SLA Availability 99.5%
P95 Latency 8s
Maintenance Window Sun 03:00-04:00 UTC
Default Input Modes application/json, multipart/form-data, text/plain
Default Output Modes application/json, text/markdown

Per-Skill Limits

Worker Límite
url_worker 5.000 URLs/task, 300s, 60 RPM
archive_worker 200 MB, 120s
document_worker 50 MB, 60s
media_worker 500 MB, 300s, 2 concurrent
ai_worker 200K chars, 120s, 60 RPM
gemini_generalist_worker 100K chars, 120s, 30 RPM

---

🔐 Security

Scheme Type Description
bearer HTTP Bearer Optional API key for authenticated clients
x402 x402 v1 Pay-per-task in USDC on Base via PayAI

Nunca compartir las siguientes variables (solo en Railway env):

· GEMINI_API_KEY
· SUPABASE_ANON_KEY
· AGENT_API_KEY
· HAMSA_API_KEY

---

🧪 Usage Examples

Bulk URL Check (500 URLs)

```bash
curl -X POST https://practical-ambition-production.up.railway.app/api/v1/agent/execute \
  -H "Content-Type: application/json" \
  -H "X-PAYMENT: <x402-receipt>" \
  -d '{
    "skill": "url_worker",
    "input": {
      "urls": [
        "https://example.com",
        "https://example.org",
        "..."
      ]
    }
  }'
```

PDF → Markdown

```bash
curl -X POST https://practical-ambition-production.up.railway.app/api/v1/agent/execute \
  -H "Content-Type: multipart/form-data" \
  -H "X-PAYMENT: <x402-receipt>" \
  -F "skill=document_worker" \
  -F "operation=pdf_to_markdown" \
  -F "file=@documento.pdf"
```

Extract Audio from Video (FFmpeg)

```bash
curl -X POST https://practical-ambition-production.up.railway.app/api/v1/agent/execute \
  -H "Content-Type: multipart/form-data" \
  -H "X-PAYMENT: <x402-receipt>" \
  -F "skill=media_worker" \
  -F "operation=extract_audio" \
  -F "format=mp3" \
  -F "file=@video.mp4"
```

Extract ZIP

```bash
curl -X POST https://practical-ambition-production.up.railway.app/api/v1/agent/execute \
  -H "Content-Type: multipart/form-data" \
  -H "X-PAYMENT: <x402-receipt>" \
  -F "skill=archive_worker" \
  -F "operation=extract" \
  -F "file=@archivo.zip"
```

AI Text Generation

```bash
curl -X POST https://practical-ambition-production.up.railway.app/api/v1/agent/execute \
  -H "Content-Type: application/json" \
  -H "X-PAYMENT: <x402-receipt>" \
  -d '{
    "skill": "ai_worker",
    "input": {
      "prompt": "Write a 500-word article about A2A agents",
      "language": "en"
    }
  }'
```

---

🗂️ Public Registries

Registry URL
A2A Registry https://a2aregistry.org/agents
x402 Bazaar https://facilitator.payai.network/discovery/resources
Coinbase CDP https://api.cdp.coinbase.com/platform/v2/x402/discovery/merchant?payTo=0xdE732Ef88Eabd42e6510a38c2D191B74FD566C0B
PayAI Bazaar https://facilitator.payai.network/discovery/resources
Agentic.Market https://agentic.market

---

🔍 SEO & Discovery

Keywords (full list)

```
pdf-to-markdown, pdf-extractor, audio-extractor, ffmpeg-transcoder,
python-execution, code-sandbox, web-scraper, bulk-url-checker,
csv-to-json, zip-extractor, ai-researcher, data-parser,
media-processing, gemini-ai, token-optimization, a2a-agent,
omnitask-agent, multi-worker, x402-merchant, payai,
a2a, mcp, mcp-server, autonomous-agent, developer-tools,
data-processing, document-parser, media-transcoder,
ai-code-generation, rag-preprocessing, presentation-generator,
book-writer, bot-builder, website-generator, apk-code-generator,
json-to-csv, yaml-parser, docx-parser, archive-extractor,
video-transcoder, content-generation, research-agent,
translation-agent, code-review, python-sandbox,
free-agent, cheap-agent, fast-agent, 24-7-agent,
usdc-payment, base-network, evm-agent, solana-agent,
micropayments, pay-per-task, agent-to-agent
```

Intents

```
convert_document, extract_audio, transcode_media, run_python_code,
scrape_urls, analyze_data, unzip_archive, generate_content,
research_topic, bulk_url_check, translate_text, review_code,
generate_website, generate_bot, generate_apk, generate_book,
generate_presentation, preprocess_media, parse_pdf,
extract_metadata, validate_urls, compress_archive
```

Use Cases

· Bulk URL validation for SEO audits
· PDF→Markdown conversion for RAG pipelines
· Media preprocessing to reduce LLM token cost
· Automated research memos with citations
· Pay-per-task x402 micropayments via PayAI
· Bot source-code generation (Telegram, Discord, WhatsApp, X)
· Ready-to-deploy website generation
· Ebook / presentation / documentation generation
· APK source code generation and review
· Multi-language translation at scale
· Archive decompression and tree inspection
· Video-to-audio extraction for transcription pipelines
· JSON ↔ CSV ↔ YAML conversions at scale
· Code review and improvement suggestions

Especialidades (SEO ES)

```
web-scraper, bulk-url-checker, pdf-to-markdown, document-converter,
archive-extractor, ffmpeg-transcoder, media-processor, audio-extractor,
ai-code-generation, code-review, translation, research-agent,
data-analysis, content-generation, rag-preprocessing, a2a-agent,
x402-merchant, multi-worker, omnitask-agent, python-sandbox,
presentation-generator, book-writer, bot-builder, website-generator,
apk-code-generator, generador-de-codigo, transductor-de-medios,
extractor-de-audio, validador-de-urls, conversor-de-documentos
```

Specialties (SEO EN)

```
web-scraper, bulk-url-checker, pdf-to-markdown, document-converter,
archive-extractor, ffmpeg-transcoder, media-processor, audio-extractor,
ai-code-generation, code-review, translation, research-agent,
data-analysis, content-generation, rag-preprocessing, a2a-agent,
x402-merchant, multi-worker, omnitask-agent, python-sandbox,
presentation-generator, book-writer, bot-builder, website-generator,
apk-code-generator, code-generator, media-transcoder,
audio-extractor, url-validator, document-converter
```

---

🌍 Multilingual Description

🇪🇸 Español

Agente A2A autónomo multi-worker de alto rendimiento especializado en pre-procesamiento masivo de archivos a coste cero, parsing determinista de documentos y medios, scraping web paralelo a gran escala, generación de código, creación de contenido estructurado y ejecución de tareas complejas con Gemini AI. Ideal para pipelines RAG, automatización industrial de datos, generación de activos digitales y ejecución de miles de tareas concurrentes 24/7.

🇬🇧 English

Autonomous multi-worker A2A agent specialized in zero-cost mass file pre-processing, deterministic document & media parsing, large-scale parallel web scraping, code generation, structured content creation, and complex task execution powered by Gemini AI. Built for RAG pipelines, industrial data automation, digital asset generation, and high-volume concurrent task execution 24/7.

---

📋 Copy-Paste por tipo de formulario

🔹 Agentic Market (repo/spec)

```
https://practical-ambition-production.up.railway.app/.well-known/agent.json
```

🔹 AgentsAccess (name + capabilities)

```json
{
  "name": "Dealwork-MegaWorkers",
  "description": "Autonomous multi-worker A2A agent specialized in file pre-processing, document parsing, media transcoding, and Gemini AI execution",
  "capabilities": ["url-checker", "pdf-parser", "archive-extract", "media-transcode", "ai-generation", "code-review", "translation"],
  "website": "https://practical-ambition-production.up.railway.app",
  "contact": "manu_shop@icloud.com"
}
```

🔹 Pocodot (extended metadata)

```json
{
  "name": "Dealwork-MegaWorkers",
  "tagline": "Omnitask A2A agent: URL, archive, document, media, AI",
  "description": "Autonomous multi-worker A2A agent with 6 specialized workers: bulk URL checking, archive extraction, PDF/JSON/CSV parsing, FFmpeg media transcoding, Gemini AI generation, and general reasoning fallback.",
  "category": "developer_tools",
  "complexity": "intermediate",
  "setup_time": "1 min",
  "connections": ["HTTP", "x402"],
  "tags": ["a2a", "x402", "multi-worker", "gemini", "ffmpeg", "pdf-parser", "web-scraper"],
  "author_name": "Dealwork",
  "author_email": "manu_shop@icloud.com",
  "website": "https://practical-ambition-production.up.railway.app"
}
```

🔹 GitHub PR (formato AGENT.md)

```markdown
# Dealwork-MegaWorkers
## [Dealwork MegaWorkers](https://practical-ambition-production.up.railway.app)
![thumbnail_picture](https://dealwork.ai/static/icon.png)

Autonomous multi-worker A2A agent specialized in file pre-processing, document parsing, and Gemini AI execution.

### Website
https://practical-ambition-production.up.railway.app

### Description
6 workers: url_worker (bulk URL check), archive_worker (zip/tar), document_worker (PDF/JSON/CSV), media_worker (FFmpeg), ai_worker (Gemini), gemini_generalist (reasoning). x402 payments on Base.

### Category
Coding Agent

### Tags
a2a, x402, multi-worker, gemini, ffmpeg, pdf-parser

### Contact
manu_shop@icloud.com

### Links
https://practical-ambition-production.up.railway.app/.well-known/agent.json

```

---

📜 License

MIT License — ver LICENSE para más detalles.

---

🤝 Contributing

¿Quieres integrar Dealwork MegaWorkers en tu plataforma A2A o pipeline? Abre un issue o contacta:

📧 manu_shop@icloud.com

---

<!--
  ═══════════════════════════════════════════════════════════════════════════
  SEO FOOTER (keywords ocultas para indexación):
  a2a agent, mcp server, multi-worker agent, web scraper, bulk url checker,
  pdf to markdown, ffmpeg transcoder, gemini ai agent, x402 merchant,
  usdc base, payai, autonomous agent, developer tools, data processing,
  rag pipeline, document parser, media processor, python sandbox,
  code generation, bot builder, website generator, apk code generator,
  book writer, presentation generator, omnitask agent, agente a2a,
  agente multi-worker, raspador web, validador de urls, pdf a markdown,
  transcodificador ffmpeg, agente gemini ai, comerciante x402,
  usdc base, payai, agente autónomo, herramientas de desarrollo,
  procesamiento de datos, pipeline rag, parser de documentos,
  procesador de medios, sandbox python, generación de código,
  constructor de bots, generador de webs, generador de apks,
  escritor de libros, generador de presentaciones, agente omnitask,
  cheap agent, fast agent, 24-7 agent, micropayments, pay per task,
  agent to agent, free tier, bulk processing, high volume agent,
  parallel processing, deterministic parsing, zero token cost
  ═══════════════════════════════════════════════════════════════════════════
