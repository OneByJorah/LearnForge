<!-- j1-brand:v2 -->
<div align="center">

# IT Training System

A self-hosted platform for managing IT training — structured learning paths, AI-generated quizzes, trainee progress tracking, and video ingestion.

[![GitHub](https://img.shields.io/badge/github-OneByJorah%2Fit--training--system-FFB300?style=for-the-badge&labelColor=0d0d0c)](https://github.com/OneByJorah/it-training-system)
[![License](https://img.shields.io/badge/license-MIT-FFB300?style=for-the-badge&labelColor=0d0d0c)](LICENSE)
[![Language](https://img.shields.io/badge/Python-FFB300?style=for-the-badge&labelColor=0d0d0c)](https://python.org)
[![Built by](https://img.shields.io/badge/built%20by-JorahOne%20LLC-FFB300?style=for-the-badge&labelColor=0d0d0c)](https://github.com/OneByJorah)

</div>

---

## Why This Exists

Building and maintaining IT training programs is slow — writing quiz questions by hand, tracking who's completed what, and keeping content organized across teams. This system automates the heavy parts: AI-generated quizzes via Ollama, structured learning paths with progress tracking, video content managed through MinIO, and semantic search over training materials powered by Qdrant.

## Key Features

| Feature | Why It Matters |
|---|---|
| AI-generated quizzes | Ollama creates questions from training content automatically |
| Structured learning paths | Define curricula with prerequisites and milestones |
| Trainee progress tracking | See who's completed what, across the whole org |
| Video ingestion (MinIO) | Upload and serve training videos from S3-compatible storage |
| Semantic search (Qdrant) | Find training materials by meaning, not just keywords |
| Hermes AgentOS integration | Training system plugs into your existing agent ecosystem |

## Quick Start

```bash
git clone https://github.com/OneByJorah/it-training-system.git
cd it-training-system
cp compose.env.example .env   # configure database, Ollama, MinIO, etc.
docker compose up -d
```

The API will be available at `http://localhost:8080`.

## Architecture

```
┌──────────┐     ┌──────────┐     ┌──────────────┐
│  Browser  │────▶│  FastAPI  │────▶│  PostgreSQL   │
│  (UI)     │     │  Backend   │     │  / SQLite     │
└──────────┘     └──────┬───┘     └──────────────┘
                         │
              ┌──────────┼──────────┐
              ▼          ▼          ▼
       ┌──────────┐ ┌──────────┐ ┌──────────┐
       │  Qdrant  │ │  MinIO   │ │  Ollama  │
       │  Vector   │ │  Video   │ │  AI Quiz  │
       │  Search   │ │  Storage  │ │  Engine   │
       └──────────┘ └──────────┘ └──────────┘
```

## Documentation

| Doc | Description |
|---|---|
| [Setup Guide](docs/setup.md) | Deployment and configuration |
| [Content Management](docs/content.md) | Creating learning paths and uploading materials |
| [Quiz Engine](docs/quizzes.md) | Configuring AI-generated assessments |

---

## License

MIT © JorahOne, LLC — see [LICENSE](LICENSE)

<sub>Part of the JorahOne infrastructure ecosystem.</sub>
