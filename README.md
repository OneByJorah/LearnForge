<div align="center">

![LearnForge banner](docs/assets/banner.svg)

# LearnForge

**Self-hosted IT training platform** — learning paths, AI quizzes, progress tracking, video ingestion, and certification.

[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.11%2B-3776ab?logo=python&logoColor=fff)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.100%2B-009688?logo=fastapi&logoColor=fff)](https://fastapi.tiangolo.com)
[![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?logo=docker&logoColor=fff)](https://docker.com)
[![Ollama](https://img.shields.io/badge/Ollama-Local%20LLM-000?logo=ollama&logoColor=fff)](https://ollama.ai)

</div>

---

## What It Does

LearnForge is a **production-ready, self-hosted IT training platform** designed for teams that need structured learning without cloud dependencies. It combines FastAPI backend, Qdrant vector search, MinIO object storage, and Ollama-powered AI quizzes into a single Docker Compose deployment.

## Quick Start

```bash
git clone https://github.com/OneByJorah/LearnForge.git
cd LearnForge
cp compose.env.example .env
docker compose up -d
```

API available at **http://localhost:8080**

## Features

- **Learning Paths** — Structured IT training curricula with prerequisites
- **AI-Powered Quizzes** — Auto-generated quizzes using Ollama local LLMs
- **Progress Tracking** — Monitor trainee progress and completion rates
- **Video Ingestion** — Training media via MinIO (S3-compatible)
- **Semantic Search** — Qdrant vector search for content discovery
- **Telegram Bot** — Notifications and interactive learning
- **FastAPI Backend** — Modern async Python API with auto-docs
- **Fully Self-Hosted** — No cloud services, no data leaves your network

## Tech Stack

| Component | Technology | Purpose |
|-----------|------------|---------|
| Backend | Python, FastAPI, SQLAlchemy | Async API server |
| Database | SQLite | Persistent storage |
| Vector Store | Qdrant | Semantic search |
| Object Storage | MinIO | Video/file storage |
| LLM | Ollama | AI quiz generation |
| Notifications | Telegram Bot | Learning reminders |
| Deployment | Docker Compose | One-command stack |

## Use Cases

1. **IT Teams** — Onboard new hires with structured training
2. **MSPs** — Certify technicians on internal tools
3. **Schools** — Deliver IT curriculum with automated assessment
4. **Self-Learners** — Build personal knowledge bases with AI quizzing

## License

MIT © Jhonattan L. Jimenez (OneByJorah)

---

<p align="center">Built with 🌴 by <a href="https://github.com/OneByJorah">OneByJorah</a> · <a href="https://jorahone.com">jorahone.com</a></p>
