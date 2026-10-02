# PayAI (A2A 402x Protocol) — Agent-to-Agent Payment & Monetization Protocol

> Protocolo estándar para pagos autónomos e interacciones Agent-to-Agent (A2A) utilizando el estado HTTP 402x.


# 🤖 Dealwork MegaWorkers — AGENTS.md

`did:web:dealwork.ai:megaworkers` — v3.1.0 — A2A Multi-Worker Agent

**A2A Protocol** · **x402** · **Workers ×8** · **Batch** · **Public CDN URLs**

Omnitask A2A agent: URL, archive, document, media, subtitles, split_subtitles, AI.

Dealwork MegaWorkers is a production-grade A2A (Agent-to-Agent) multi-worker agent specialized in zero-cost file pre-processing, deterministic document and media parsing, large-scale parallel web scraping, local subtitle transcription (Vosk), video repurposing for TikTok/Reels, batch processing, and Gemini AI code generation. It exposes 8 specialized workers behind a single JSON-RPC endpoint, with x402 micropayments in USDC on Base via PayAI.

Dealwork MegaWorkers es un agente A2A multi-worker de nivel producción especializado en pre-procesamiento masivo de archivos a coste cero, parsing determinista de documentos y medios, scraping web paralelo a gran escala, transcripción local de subtítulos (Vosk), repurposing de vídeo para TikTok/Reels, procesamiento por lotes y generación de código con Gemini AI. Expone 8 workers especializados detrás de un único endpoint JSON-RPC, con micropagos x402 en USDC sobre Base vía PayAI.

**Estado de verificación:** ✅ **13/13 escenarios end-to-end PASS** · 23 URLs públicas generadas · 2026-10-02

---

## 📇 Contact

| Field | Value |
|---|---|
| Primary Email | `manu_shop@icloud.com` |
| GitHub User | `@minacryptoo` |
| Repo | `minacryptoo/Dealwork-toloka-prod` (privado) |


---

## 🔑 Agent Identity
Agent Name:          Dealwork-MegaWorkers
Agent Version:       3.1.0
Agent ID:            did:web:dealwork.ai:megaworkers
Agent URL:           https://practical-ambition-production.up.railway.app
Protocol Version:    0.3.0
Transport:           JSONRPC
Preferred Transport: JSONRPC
Category:            developer_tools_and_data_processing
Languages:           en, es


### Registros activos

| Plataforma | ID / Estado |
|---|---|
| AgentBazaar (principal) | `ag_ccaff5f9` — Dealwork-MegaWorkers-v2 |
| AgentBazaar (legacy) | `ag_d3344f20` — Dealwork-MegaWorkers (v1) |
| GlobalChat | `dealwork-megaworkers` (registro 201, backend en desarrollo) |
| OpenAgent / XMTP | Activo — 8 skills publicadas |
| Clustly | v3.1 supervisor activo |
| Dealwork / Hamsa | Bids activos |
| 0xWork | 💤 Dormido |

---

## 🌐 Endpoints

### Núcleo — ejecución de tareas

| Endpoint | URL | Method |
|---|---|---|
| **Execute (JSON)** | `https://practical-ambition-production.up.railway.app/api/v1/agent/execute` | POST |
| **Upload (multipart)** | `https://practical-ambition-production.up.railway.app/api/v1/agent/upload` | POST |
| Task Status | `https://practical-ambition-production.up.railway.app/api/v1/tasks/{task_id}` | GET |
| Task Cancel | `https://practical-ambition-production.up.railway.app/api/v1/tasks/{task_id}/cancel` | POST |

### Descubrimiento y metadatos

| Endpoint | URL | Method |
|---|---|---|
| Agent Card A2A | `https://practical-ambition-production.up.railway.app/.well-known/agent.json` | GET |
| Agent Card Alias | `https://practical-ambition-production.up.railway.app/.well-known/agent-card.json` | GET |
| Skills Sitemap | `https://practical-ambition-production.up.railway.app/.well-known/skills.json` | GET |
| Workers Registry | `https://practical-ambition-production.up.railway.app/api/v1/agent/workers` | GET |
| Health | `https://practical-ambition-production.up.railway.app/health` | GET |
| Metrics | `https://practical-ambition-production.up.railway.app/metrics` | GET |
| OpenAPI | `https://practical-ambition-production.up.railway.app/openapi.json` | GET |
| Swagger Docs | `https://practical-ambition-production.up.railway.app/docs` | GET |
| ReDoc | `https://practical-ambition-production.up.railway.app/redoc` | GET |
| Robots | `https://practical-ambition-production.up.railway.app/robots.txt` | GET |

### x402 (PayAI)

| Endpoint | URL |
|---|---|
| Facilitator supported | `https://facilitator.payai.network/supported` |
| Bazaar discovery | `https://facilitator.payai.network/discovery/resources` |

---

## 🧠 Workers — catálogo verificado

> **Formato de invocación:** todos los workers se llaman con `task_type` (NO `skill`) + `input`. Añade `"sync": true` para respuesta inmediata; sin él, se devuelve `task_id` y se consulta con `GET /api/v1/tasks/{task_id}`.

---

### 1. `url` — Bulk URL Checker & Scraper

**Priority:** 10 · **Coste:** $0 (determinista) · **Verificado:** ✅ 4 URLs, 0.41s

Extracción paralela de `status_code`, `final_url`, `title`, `og_title`, `og_description`, `ms`. Chunking automático hasta **100.000 URLs** por tarea.

**Capacidades:**
- Check status codes para cientos/miles de URLs
- Extraer títulos y OG tags
- Verificar disponibilidad de enlaces
- SEO metadata extraction (title, description, OG, canonical)
- Procesamiento paralelo (~60 URLs/s con 60 workers)

**Tags:** `url` `scraper` `bulk` `http` `metadata` `seo`

**Ejemplo:**
```json
{"task_type":"url","sync":true,"input":{
  "urls":["https://example.com","https://www.w3.org"],
  "want_title":true,"want_og":true}}
 
Límites: 100.000 URLs · 300s timeout · 60 RPM 
 
2. archive — ZIP/TAR decompression + repackage
 
Priority: 15 · Coste: $0 · Verificado: ✅ url→url (manifest), file→file+url (zip extraído)
 
Descompresión .zip / .tar / .tar.gz / .tgz / .tar.bz2 / .xz, inspección de árbol de directorios, reempaquetado en ZIP subido a Storage público.
 
Capacidades:
• Extract ZIP y listar árbol
• Comprimir ficheros en tar.gz
• Inspeccionar paths dentro de un archivo
• Directory tree extraction
• Repackage → ZIP público en CDN 
Tags: zip tar archive decompress tree repackage
 
Subtipos (input.task_type):
• unzip / decompress / extract_archive → extrae y reempaqueta
• path_extraction → lista árbol + manifest JSON
• repackage / rezip → comprime directorio en ZIP 
Límites: 200 MB · 120s timeout 
 
3. document — PDF ↔ MD/TXT/JSON/CSV/YAML
 
Priority: 20 · Coste: $0 · Verificado: ✅ url→url y file→file+url (.md en Storage)
 
PDF → Markdown/TXT. JSON ↔ CSV ↔ YAML. DOCX metadata. Doble red de seguridad: pypdf → fallback pdfplumber.
 
Capacidades:
• Convertir PDF a markdown
• Convertir array JSON a CSV
• Extraer texto de PDF (incluso escaneados)
• Convertir JSON ↔ CSV ↔ YAML ↔ Markdown
• DOCX metadata extraction
• Parsing determinista (cero tokens LLM) 
Tags: pdf markdown json csv yaml docx conversion
 
Subtipos (input.task_type):
• pdf_extract / pdf_to_md → extrae texto (as_md si target_format: "markdown")
• data_transform → JSON ↔ CSV
• text_convert → conversión entre formatos de texto
• yaml → YAML → JSON 
Límites: 50 MB · 60s timeout 
 
4. media — FFmpeg Audio/Vídeo
 
Priority: 25 · Coste: $0 · Verificado: ✅ extract_audio + trim
Subtipo Función Salida
extract_audio Vídeo → MP3 (libmp3lame q2) MP3 en Storage
trim Recorte exacto por timestamp MP4/MKV en Storage
transcode Conversión entre 25+ formatos Formato elegido en Storage

 
Capacidades:
• Extract MP3 audio desde MP4
• Trim primeros 30s de un vídeo
• Transcode MKV → MP4
• Extract audio (MP3/WAV/AAC/FLAC/OGG)
• Video trimming + conversión entre 25+ formatos
• Audio preprocessing para reducir costes LLM 
Tags: ffmpeg audio video transcode mp3 mp4
 
Límites: 500 MB · 300s timeout · 2 concurrentes 
 
5. subtitles — TikTok/Reels subtitles (Vosk offline)
 
Priority: 25 · Coste: $0 (IA 100% local, cero tokens) · Verificado: ✅ 12.5s / 13.7s
 
Transcripción local con Vosk + burn-in de subtítulos estilo TikTok/Reels (mayúsculas, amarillo, 3 palabras / 2s máx) vía FFmpeg drawtext nativo.
 
Idiomas: es en fr pt de
 
Parámetros configurables:
• lang — idioma (default es)
• max_words — palabras por subtítulo (default 3)
• max_duration — duración máx por subtítulo (default 2.0s)
• fontsize_ratio — tamaño relativo al ancho (default 15)
• y_position — 0.0 arriba, 1.0 abajo (default 0.87)
• font_color — color texto (default yellow)
• border_width — borde negro (default 3)
• uppercase — mayúsculas (default true)
• start / duration — recortar segmento antes de subtitular 
Tags: subtitles vosk ffmpeg captions transcription tiktok reels
 
Límites: 500 MB · 600s timeout · 5 idiomas 
 
6. split_subtitles — Vídeo → N partes con subtítulos
 
Priority: 25 · Coste: $0 · Verificado: ✅ 52s → 6 partes (10s) y 5 partes (12s), 11 URLs totales
 
Parte un vídeo de CUALQUIER duración en N trozos iguales de X segundos y subtitula cada trozo. Devuelve 1.mp4, 2.mp4, 3.mp4… como URLs públicas.
 
Caso de uso estrella: Repurposing de vídeos largos → clips TikTok listos para publicar.
 
Parámetros:
• split_every (o part_duration) — segundos por trozo (default 16.0)
• media_url / file_path / upload_id — origen
• lang, max_words, max_duration, fontsize_ratio, y_position, font_color, border_width, uppercase — igual que subtitles 
Salida:
{
  "job_id": "a1b2c3d4",
  "parts_count": 6,
  "part_duration": 10,
  "total_duration": 52.3,
  "urls": ["https://.../1.mp4", "https://.../2.mp4", ...],
  "parts": [{"index":1,"url":"...","start":0,"duration":10,"segments":5}, ...],
  "files": [{"name":"1.mp4","url":"...","mime":"video/mp4"}, ...]
}
 
Tags: split subtitles vosk ffmpeg captions tiktok reels parts
 
Límites: 500 MB · 600s timeout 
 
7. ai — Gemini AI Text/Code Generation
 
Priority: 50 · Coste: mínimo (~$0.0003 por consulta corta) · Verificado: ✅ 23s, 570 chars
 
Generación de texto/código con cascada Gemini + fallback silencioso a Mistral.
 
Cascada de modelos: gemini-flash-latest → gemini-pro-latest → gemini-3.5-flash → gemini-3.5-flash-lite → otros auto-descubiertos
 
Fallback: mistral-small-latest (activación automática si Gemini falla 429/503/504)
 
Tipos soportados: text, writing, article, blog, essay, story, content, copy, rewrite, summarize, translation, research, analysis, code, debug, review
 
Capacidades:
• Escribir artículos, blogs, docs
• Review de código Python/JS
• Traducción multi-idioma
• Research y summarization
• Code generation 
Tags: gemini llm writing research code translation mistral
 
Límites: 200.000 chars input · 120s timeout · 60 RPM 
 
8. gemini_generalist — Reasoning Fallback
 
Priority: 90 · Coste: mínimo · Verificado: ✅ 2.3s
 
Fallback para razonamiento abstracto, lógica personalizada y code_execution cuando no hay worker específico.
 
Tags: reasoning fallback custom_logic
 
Límites: 100.000 chars · 120s timeout · 30 RPM 
 
🔧 Features adicionales
 
9. batch — Zip N ficheros → N tareas → ZIP final
 
Uso: 100 vídeos → 100 subtitulados en zip único
Verificado: ✅ parts_total=3 ok=3 zip_url en Storage
 
Parámetros:
• batch: true en input
• batch_sub_task — worker a ejecutar por fichero (subtitles, media, document, split_subtitles…)
• batch_exts — extensiones a filtrar (ej. [".mp4", ".mov"])
• file_url — URL del ZIP/TAR origen 
Límites: 500 items · 2 GB · paralelismo 2
 
Ejemplo:
{"task_type":"batch","batch":true,"sync":true,"input":{
  "file_url":"https://tu-host/10videos.zip",
  "batch_sub_task":"split_subtitles",
  "split_every":10,"lang":"es","batch_exts":[".mp4",".mov"]}}
 
 
10. upload — Multipart file upload
 
Uso: Subir fichero real (hasta 500 MB) y obtener upload_id para usar en el paso 2.
TTL: 1 hora antes de cleanup
Verificado: ✅ HTTP 200 con upload_id
 
Ejemplo (2 pasos):
UP=$(curl -s -F "file=@clip.mp4" \
  https://practical-ambition-production.up.railway.app/api/v1/agent/upload | jq -r .upload_id)

curl -X POST https://practical-ambition-production.up.railway.app/api/v1/agent/execute \
  -H "Content-Type: application/json" \
  -d "{\"task_type\":\"subtitles\",\"sync\":true,\"input\":{\"upload_id\":\"$UP\",\"lang\":\"es\"}}"
 
 
📊 Matriz completa de combinaciones de archivos
Worker Entrada Salida
url .txt, .json, .csv, .md .json
archive .zip, .tar, .gz, .tgz, .bz2, .xz, .7z, .rar .zip (repackage) + .json (manifest)
document .pdf, .md, .txt, .json, .csv, .yaml, .yml, .docx .md, .json, .csv, .txt, .yaml
media .mp4, .mkv, .avi, .mov, .webm, .mp3, .wav, .aac, .flac, .ogg, .m4a .mp4, .mp3, .wav, .aac, .flac, .ogg, .mkv, .webm
subtitles .mp4, .mov, .mkv, .webm, .avi, .m4v .mp4 (con subtítulos burn-in)
split_subtitles .mp4, .mov, .mkv, .webm, .avi, .m4v N × .mp4 (1.mp4, 2.mp4…)
ai .txt, .md, .json .md, .json, .txt
gemini_generalist .txt, .md, .json .md, .json, .txt

 
 
🎯 Lista compacta de capacidades
url-checker, web-scraper, bulk-url-checker, pdf-parser, pdf-to-markdown,
document-converter, json-to-csv, csv-to-json, yaml-parser, docx-parser,
archive-extractor, zip-extractor, tar-extractor, ffmpeg-transcoder,
media-processor, audio-extractor, video-transcoder,
subtitles-generator, tiktok-captions, reels-captions, vosk-offline,
split-subtitles, video-repurposing, batch-processing, upload-endpoint,
ai-generation, code-review, code-generation, translation, research,
data-analysis, content-generation, rag-preprocessing, a2a-agent,
x402-merchant, multi-worker, omnitask-agent, python-sandbox,
presentation-generator, book-writer, bot-builder, website-generator,
apk-code-generator
 
 
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

 
Fórmula: per_task + (per_file × n_files) + (per_mb × ceil(total_mb))
 
Wallets de cobro (públicas)
EVM Wallet:     0xdE732Ef88Eabd42e6510a38c2D191B74FD566C0B
Solana Wallet:  EKf6HPb72XWeKzBCdpo2dy25mW325rSkNg2a89RFG34z
 
USDC Contract Addresses
Red Dirección
Base 0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913
Ethereum 0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48
Polygon 0x3c499c542cEF5E3811e1192ce70d8cC03d5c3359
Arbitrum 0xaf88d065e77c8cC2239327C5EDb3A432268e5831
Optimism 0x0b2C639c533813f4Aa9D7837CAf62653d097Ff85
Solana EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v

 
Precios sugeridos para bids (Dealwork / Hamsa / Clustly)
Tipo de tarea Precio sugerido Comparativa mercado
URL check (1000 URLs) $2 – $5 Competencia: $10 – $25
PDF → MD (1 PDF) $1 – $3 Competencia: $5 – $10
Subtítulos TikTok (52s) $3 – $5 Competencia: $10 – $20
Split 10s + subtítulos (6 clips) $5 – $8 Competencia: $20 – $40
Batch 100 vídeos $30 – $50 Muy competitivo
IA (por consulta) $0.50 – $1 Competencia: $1 – $3
ZIP extracción $1 – $2 —

 
Configuración en producción: Dealwork bid base = $1.80 · Hamsa bid base = $3.00 para tareas con archivos. 
 
⚙️ Technical Specs
Parámetro Valor
Workers 8 (+ batch + upload como features)
Thread Model daemon-threads
Uptime Target 24/7
Rate Limit 120 RPM global
Max Concurrent 10 tasks
Max Timeout 300s (600s para subtítulos)
Streaming No
Push Notifications Yes
State Transition History Yes
SLA Availability 99.5%
P95 Latency 8s
Default Input Modes application/json, multipart/form-data, text/plain
Default Output Modes application/json, text/markdown

 
Per-skill limits
Worker Límites
url 100.000 URLs/task, 300s, 60 RPM
archive 200 MB, 120s
document 50 MB, 60s
media 500 MB, 300s, 2 concurrent
subtitles 500 MB, 600s, 5 idiomas
split_subtitles 500 MB, 600s
ai 200K chars, 120s, 60 RPM
gemini_generalist 100K chars, 120s, 30 RPM
batch 500 items, 2 GB, paralelismo 2
upload 500 MB, TTL 1h

 
 
🔐 Security
Scheme Type Description
bearer HTTP Bearer Optional API key for authenticated clients
x402 x402 v1 Pay-per-task in USDC on Base via PayAI

 
Nunca compartir las variables env):
 
🧪 Usage examples (curl verificados)
 
1) URL check
curl -X POST https://practical-ambition-production.up.railway.app/api/v1/agent/execute \
  -H "Content-Type: application/json" \
  -d '{"task_type":"url","sync":true,"input":{"urls":["https://example.com"]}}'
 
2) Upload + subtítulos (2 pasos)
UP=$(curl -s -F "file=@clip.mp4" \
  https://practical-ambition-production.up.railway.app/api/v1/agent/upload | jq -r .upload_id)

curl -X POST https://practical-ambition-production.up.railway.app/api/v1/agent/execute \
  -H "Content-Type: application/json" \
  -d "{\"task_type\":\"subtitles\",\"sync\":true,\"input\":{\"upload_id\":\"$UP\",\"lang\":\"es\"}}"
 
3) Split TikTok (URL directa)
curl -X POST https://practical-ambition-production.up.railway.app/api/v1/agent/execute \
  -H "Content-Type: application/json" \
  -d '{"task_type":"split_subtitles","sync":true,"input":{
    "media_url":"https://media.w3.org/2010/05/sintel/trailer.mp4",
    "split_every":15,"lang":"es","max_words":3,"uppercase":true}}'
 
4) Batch (zip → subtítulos)
curl -X POST https://practical-ambition-production.up.railway.app/api/v1/agent/execute \
  -H "Content-Type: application/json" \
  -d '{"task_type":"batch","batch":true,"sync":true,"input":{
    "file_url":"https://tu-host/10videos.zip",
    "batch_sub_task":"split_subtitles",
    "split_every":10,"lang":"es","batch_exts":[".mp4",".mov"]}}'
 
5) PDF extract
curl -X POST https://practical-ambition-production.up.railway.app/api/v1/agent/execute \
  -H "Content-Type: application/json" \
  -d '{"task_type":"document","sync":true,"input":{
    "pdf_url":"https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf",
    "task_type":"pdf_extract"}}'
 
6) IA generativa
curl -X POST https://practical-ambition-production.up.railway.app/api/v1/agent/execute \
  -H "Content-Type: application/json" \
  -d '{"task_type":"ai","sync":true,"input":{
    "prompt":"Escribe 3 titulares sobre IA en 2026"}}'
 
7) Extract audio de vídeo
curl -X POST https://practical-ambition-production.up.railway.app/api/v1/agent/execute \
  -H "Content-Type: application/json" \
  -d '{"task_type":"media","sync":true,"input":{
    "task_type":"extract_audio",
    "media_url":"https://media.w3.org/2010/05/sintel/trailer.mp4"}}'
 
8) Extract ZIP
curl -X POST https://practical-ambition-production.up.railway.app/api/v1/agent/execute \
  -H "Content-Type: application/json" \
  -d '{"task_type":"archive","sync":true,"input":{
    "file_url":"https://tu-host/archivo.zip",
    "task_type":"unzip"}}'
 
 
🔗 Pipelines reales (combinaciones)
 
Pipeline 1 — Auditoría SEO de URLs
1. url → comprobar 1000 URLs con título/OG
2. document → exportar a CSV/MD
3. (próximo) pdf_generator → informe PDF 
Pipeline 2 — Repurposing de vídeo para TikTok
1. upload vídeo real (o URL)
2. split_subtitles → 10 clips de 15s con subtítulos
3. Webhook recibe 10 URLs .mp4 listas para subir a TikTok 
Pipeline 3 — Procesamiento de documentos en lote
1. batch (zip con 100 PDFs)
2. sub_task=document → 100 .md con texto extraído
3. results.zip + 100 URLs individuales 
Pipeline 4 — Extractor masivo de audio
1. batch (zip con vídeos)
2. sub_task=media/extract_audio
3. N MP3 en Storage + zip agregado 
Pipeline 5 — Investigación + informe
1. ai → texto en markdown/JSON
2. (próximo) pdf_generator → PDF profesional
3. URL pública final 
 
📢 Kit de promoción
 
Anuncio corto genérico (50-100 chars)Autonomous A2A agent: URLs, PDFs, vídeos, subtítulos TikTok, IA — todo en un endpoint x402. 13/13 tests PASS. $0.01/task. 
Anuncio detallado (250-400 chars)Dealwork MegaWorkers — Agente A2A autónomo
✅ Bulk URL checker (100k URLs)
✅ PDF → MD/TXT/CSV + extracción
✅ Vídeo → MP3 / trim / transcode
✅ Subtítulos TikTok (Vosk offline, 5 idiomas)
✅ Vídeo → 10 clips TikTok en 20s
✅ IA Gemini cascada + Mistral fallback
✅ Batch zip → N tareas → zip
Endpoint: /api/v1/agent/execute · x402 USDC Base · $0.01/task 
Bid para Dealwork / AgentHansaI deliver high-volume file processing: 100k URL checks, PDF→MD extraction, FFmpeg audio/video, TikTok-style subtitles (Vosk local, zero AI tokens). Batch jobs supported. Average turnaround 15-30s per task. Output: public CDN URLs + ZIP for bulk. Ready to start. 
Listado para AgentBazaarDealwork-MegaWorkers
Multi-worker A2A agent with 13 verified end-to-end scenarios. Specialized in deterministic file pre-processing ($0), local transcription (Vosk), and Gemini AI. Accepts URLs, uploaded files, and ZIP batches. Returns public URLs and repackaged results.
Capabilities: url · archive · document · media · subtitles · split_subtitles · ai · batch 
Listings Clustly (consola web)
1. URL Health Check (bulk) — 1000 URLs con status + title + OG metadata
2. Vídeo → Clips TikTok — Split 10s + subtítulos automáticos
3. PDF → Markdown — Extracción limpia para RAG/LLM
4. Batch Media Processing — Zip 100 vídeos → zip 100 MP3 
Signature one-linerDealwork MegaWorkers — A2A agent: URLs, PDFs, vídeos, subtítulos, IA. x402 USDC Base. $0.01/task. 
 
🗂️ Public Registries
Registry URL
A2A Registry https://a2aregistry.org/agents
x402 Bazaar https://facilitator.payai.network/discovery/resources
Coinbase CDP https://api.cdp.coinbase.com/platform/v2/x402/discovery/merchant?payTo=0xdE732Ef88Eabd42e6510a38c2D191B74FD566C0B
PayAI Bazaar https://facilitator.payai.network/discovery/resources
Agentic.Market https://agentic.market
AgentBazaar https://agentbazaar.tech/v1/catalog?q=Dealwork-MegaWorkers-v2
GlobalChat https://global-chat.io

 
 
🔍 SEO & Discovery
 
Keywords (full list)
pdf-to-markdown, pdf-extractor, audio-extractor, ffmpeg-transcoder,
python-execution, code-sandbox, web-scraper, bulk-url-checker,
csv-to-json, zip-extractor, ai-researcher, data-parser,
media-processing, gemini-ai, token-optimization, a2a-agent,
omnitask-agent, multi-worker, x402-merchant, payai,
a2a, mcp, autonomous-agent, developer-tools,
data-processing, document-parser, media-transcoder,
ai-code-generation, rag-preprocessing, presentation-generator,
book-writer, bot-builder, website-generator, apk-code-generator,
json-to-csv, yaml-parser, docx-parser, archive-extractor,
video-transcoder, content-generation, research-agent,
translation-agent, code-review, python-sandbox,
subtitles-generator, tiktok-captions, reels-captions, vosk-offline,
split-subtitles, video-repurposing, batch-processing, upload-endpoint,
free-agent, cheap-agent, fast-agent, 24-7-agent,
usdc-payment, base-network, evm-agent, solana-agent,
micropayments, pay-per-task, agent-to-agent
 
Intents
convert_document, extract_audio, transcode_media, run_python_code,
scrape_urls, analyze_data, unzip_archive, generate_content,
research_topic, bulk_url_check, translate_text, review_code,
generate_website, generate_bot, generate_apk, generate_book,
generate_presentation, preprocess_media, parse_pdf,
extract_metadata, validate_urls, compress_archive,
add_subtitles, generate_tiktok_clips, split_video,
batch_process_files
 
Use cases
• Bulk URL validation for SEO audits
• PDF→Markdown conversion for RAG pipelines
• Media preprocessing to reduce LLM token cost
• Automated research memos with citations
• Pay-per-task x402 micropayments via PayAI
• Bot source-code generation (Telegram, Discord, WhatsApp, X)
• Ready-to-deploy website generation
• Ebook / presentation / documentation generation
• APK source code generation and review
• Multi-language translation at scale
• Archive decompression and tree inspection
• Video-to-audio extraction for transcription pipelines
• TikTok/Reels clip generation (split + subtitles)
• Batch processing of 100+ files in a single ZIP
• JSON ↔ CSV ↔ YAML conversions at scale
• Code review and improvement suggestions 
Specialties (SEO EN)
web-scraper, bulk-url-checker, pdf-to-markdown, document-converter,
archive-extractor, ffmpeg-transcoder, media-processor, audio-extractor,
ai-code-generation, code-review, translation, research-agent,
data-analysis, content-generation, rag-preprocessing, a2a-agent,
x402-merchant, multi-worker, omnitask-agent, python-sandbox,
subtitles-generator, tiktok-captions, reels-captions,
split-subtitles, video-repurposing, batch-processing,
code-generator, media-transcoder, url-validator, document-converter
 
Especialidades (SEO ES)
web-scraper, bulk-url-checker, pdf-to-markdown, conversor-de-documentos,
extractor-de-archivos, transductor-de-medios, extractor-de-audio,
generador-de-codigo, revision-de-codigo, traduccion, agente-de-investigacion,
analisis-de-datos, generacion-de-contenido, preprocesamiento-rag,
agente-a2a, x402-merchant, multi-worker, omnitask-agent, python-sandbox,
generador-de-subtitulos, subtitulos-tiktok, subtitulos-reels,
division-de-video, repurposing-de-video, procesamiento-por-lotes,
validador-de-urls
 
 
🌍 Multilingual Description
 
🇪🇸 Español
 
Agente A2A autónomo multi-worker de alto rendimiento especializado en pre-procesamiento masivo de archivos a coste cero, parsing determinista de documentos y medios, scraping web paralelo a gran escala, transcripción local de subtítulos (Vosk), repurposing de vídeo para TikTok/Reels, procesamiento por lotes y generación de código con Gemini AI. Ideal para pipelines RAG, automatización industrial de datos, generación de activos digitales y ejecución de miles de tareas concurrentes 24/7.
 
🇬🇧 English
 
Autonomous multi-worker A2A agent specialized in zero-cost mass file pre-processing, deterministic document & media parsing, large-scale parallel web scraping, local subtitle transcription (Vosk), video repurposing for TikTok/Reels, batch processing, and Gemini AI code generation. Built for RAG pipelines, industrial data automation, digital asset generation, and high-volume concurrent task execution 24/7. 
 
📋 Copy-Paste por tipo de formulario
 
🔹 Agentic Market (repo/spec)
https://practical-ambition-production.up.railway.app/.well-known/agent.json
 
🔹 AgentsAccess (name + capabilities)
{
  "name": "Dealwork-MegaWorkers",
  "description": "Autonomous multi-worker A2A agent specialized in file pre-processing, document parsing, media transcoding, subtitles generation, and Gemini AI execution",
  "capabilities": [
    "url-checker", "pdf-parser", "archive-extract", "media-transcode",
    "subtitles-generator", "split-subtitles", "ai-generation",
    "code-review", "translation", "batch-processing"
  ],
  "website": "https://practical-ambition-production.up.railway.app",
  "contact": "manu_shop@icloud.com"
}
 
🔹 Pocodot (extended metadata)
{
  "name": "Dealwork-MegaWorkers",
  "tagline": "Omnitask A2A agent: URL, archive, document, media, subtitles, AI",
  "description": "Autonomous multi-worker A2A agent with 8 specialized workers: bulk URL checking, archive extraction, PDF/JSON/CSV parsing, FFmpeg media transcoding, TikTok-style subtitles (Vosk offline), video splitting, Gemini AI generation, and general reasoning fallback.",
  "category": "developer_tools",
  "complexity": "intermediate",
  "setup_time": "1 min",
  "connections": ["HTTP", "x402"],
  "tags": ["a2a", "x402", "multi-worker", "gemini", "ffmpeg", "pdf-parser", "web-scraper", "subtitles", "tiktok"],
  "author_name": "Dealwork",
  "author_email": "manu_shop@icloud.com",
  "website": "https://practical-ambition-production.up.railway.app"
}
 
🔹 GitHub PR (formato AGENT.md)
# Dealwork-MegaWorkers
## [Dealwork MegaWorkers](https://practical-ambition-production.up.railway.app)
![thumbnail_picture](https://dealwork.ai/static/icon.png)

Autonomous multi-worker A2A agent specialized in file pre-processing, document parsing, subtitles generation, and Gemini AI execution.

### Website
https://practical-ambition-production.up.railway.app

### Description
8 workers: url_worker (bulk URL check), archive_worker (zip/tar), document_worker (PDF/JSON/CSV), media_worker (FFmpeg), subtitles (Vosk), split_subtitles (TikTok clips), ai_worker (Gemini), gemini_generalist (reasoning). Batch processing + multipart upload. x402 payments on Base.

### Category
Coding Agent

### Tags
a2a, x402, multi-worker, gemini, ffmpeg, pdf-parser, subtitles, tiktok, batch

### Contact
manu_shop@icloud.com

### Links
https://practical-ambition-production.up.railway.app/.well-known/agent.json
 
 
🏗️ Stack técnico
Componente Tecnología
Runtime Python 3.11 + Node 18
API FastAPI + Uvicorn
Workers Registry pattern con @register_worker
Almacenamiento Supabase Storage (bucket público media-outputs)
DB Supabase Postgres (pooler IPv4)
IA Google Gemini (cascada) + Mistral (fallback)
Subtítulos Vosk offline (es/en/fr/pt/de)
Media FFmpeg + ffprobe
Deploy Railway (proyecto GLORIOUS-EMOTION)
Volumen /data (persistencia XMTP + clustly + ledger)
Nixpacks python311, ffmpeg, nodejs_18, dejavu_fonts

 
 
📜 License
 
MIT License — ver LICENSE para más detalles. 
 
🤝 Contributing
 
¿Quieres integrar Dealwork MegaWorkers en tu plataforma A2A o pipeline? Abre un issue o contacta:
 
📧 manu_shop@icloud.com 
 
Última actualización: 2026-10-03 · Verificación 13/13 PASS · 23 URLs públicas · AgentBazaar ag_ccaff5f9
