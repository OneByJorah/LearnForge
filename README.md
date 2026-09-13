# LearnForge

> Self-hosted IT training platform with learning paths, Ollama-generated quizzes, progress tracking, and MinIO video storage — zero cloud dependency.

[![License](https://img.shields.io/github/license/OneByJorah/LearnForge?style=for-the-badge&color=FFB300&labelColor=0a0a09)](https://github.com/OneByJorah/LearnForge)
[![Top Language](https://img.shields.io/github/languages/top/OneByJorah/LearnForge?style=for-the-badge&color=FFB300&labelColor=0a0a09)](https://github.com/OneByJorah/LearnForge)
[![Stars](https://img.shields.io/github/stars/OneByJorah/LearnForge?style=for-the-badge&color=FFB300&labelColor=0a0a09)](https://github.com/OneByJorah/LearnForge/stargazers)
[![Last Commit](https://img.shields.io/github/last-commit/OneByJorah/LearnForge?style=for-the-badge&color=FFB300&labelColor=0a0a09)](https://github.com/OneByJorah/LearnForge/commits)
[![CI](https://img.shields.io/github/actions/workflow/status/OneByJorah/LearnForge/ci.yml?style=for-the-badge&color=FFB300&labelColor=0a0a09&label=ci)](https://github.com/OneByJorah/LearnForge/actions/workflows/ci.yml)

![LearnForge dashboard](docs/assets/screenshot.png)

## What This Is

LearnForge packages everything an IT team needs to train and certify staff into one Docker Compose stack: structured learning paths, AI-generated quizzes, trainee progress, and training video storage. The FastAPI backend, Qdrant vector store, MinIO object storage, and Ollama LLM all run on your own network, so training content and learner data never leave the building.

## Quick Start

```bash
git clone https://github.com/OneByJorah/LearnForge.git
cd LearnForge
cp compose.env.example .env    # set MINIO_ROOT_PASSWORD and SECRET_KEY
docker compose up -d
```

Open the API at **http://localhost:8080** (interactive docs at `/docs`); MinIO console is on **http://localhost:9001**.

## Features

- Learning paths with ordered curricula and per-path prerequisites.
- AI-generated quizzes and questions via a local Ollama LLM.
- Progress tracking at user, path, and team level with event timelines.
- Training-video upload into S3-compatible MinIO.
- Qdrant semantic search over course content.
- Telegram bot for learner notifications and interactive prompts.
- One-command bootstrap via `make bootstrap`.

## Architecture

```
        ┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────┐
        │  Ollama  │   │  Qdrant  │   │  MinIO   │   │training- │
        │  :11434  │   │  :6333   │   │ :9000/1  │   │api :8080 │
        └────▲─────┘   └────▲─────┘   └────▲─────┘   └────┬─────┘
             │              │              │              │
             └──────────────┴──────────────┴──────────────┘
                              Docker network
```

`training-api` waits for Qdrant, MinIO, and Ollama healthchecks before starting.

## Stack

Python 3.11 · FastAPI · SQLAlchemy · SQLite/PostgreSQL · Qdrant · MinIO · Ollama · Telegram Bot API · Docker Compose · Make.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). [Open an issue](https://github.com/OneByJorah/LearnForge/issues) to report a bug or request a feature.

## License

MIT — see [LICENSE](LICENSE).
