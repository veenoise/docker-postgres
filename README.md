# docker-postgres

A minimal Docker Compose setup for running PostgreSQL 18.4 locally.

## Prerequisites

- [Docker](https://docs.docker.com/engine/install/) with Compose plugin

## Quick Start

```bash
cp .sample.env .env    # configure your credentials
docker compose up -d   # start the database
```

## Configuration

Edit `.env` to set the database credentials:

| Variable            | Description     |
|---------------------|-----------------|
| `POSTGRES_USER`     | Database user   |
| `POSTGRES_PASSWORD` | Database password |
| `POSTGRES_DB`       | Database name   |

## Connecting

Connect at `localhost:5432` with the credentials from `.env`.

```bash
psql -h localhost -U <user> -d <db>
```

## Commands

| Action                     | Command                  |
|----------------------------|--------------------------|
| Start                      | `docker compose up -d`   |
| Stop                       | `docker compose down`    |
| View logs                  | `docker compose logs -f` |
| Destroy (keeps volume)     | `docker compose down`    |
| Destroy (removes volume)   | `docker compose down -v` |

## Data Persistence

Database files are stored in the named Docker volume `postgres-data`. Data survives container restarts and rebuilds.
