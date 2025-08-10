# DX Docker Compose Databases

This directory contains Docker Compose configurations for development databases and monitoring tools.

## Setup Instructions

1. Copy `.env.example` to `.env`:
   ```bash
   cp .env.example .env
   ```

2. Edit `.env` and update all passwords with secure values:
   - Replace all `changeme_*` passwords with strong, unique passwords
   - Adjust ports if needed (if defaults are already in use)

3. Start the services:
   ```bash
   docker-compose up -d
   ```

## Available Services

- **PostgreSQL**: Database on port 5432
- **MongoDB**: NoSQL database on port 27017
- **Redis**: Cache/message broker on port 6379
- **Elasticsearch**: Search engine on port 9200
- **Kibana**: Elasticsearch UI on port 5601
- **Jaeger**: Distributed tracing UI on port 16686
- **Grafana**: Metrics visualization on port 3000
- **OpenTelemetry Collector**: Telemetry collection on ports 4317 (gRPC) and 4318 (HTTP)

## Security Notes

- Never commit the `.env` file to version control
- Use strong, unique passwords for all services
- Consider using Docker secrets for production environments
- Regularly update container images for security patches

## Data Persistence

All data is persisted in the `./data` directory with subdirectories for each service.
