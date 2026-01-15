# Docker Uptime Kuma

A simple Docker Compose setup for [Uptime Kuma](https://github.com/louislam/uptime-kuma), a self-hosted monitoring tool.

## Prerequisites

- Docker
- Docker Compose

## Getting Started

1. **Clone the repository:**
   ```bash
   git clone <your-repo-url>
   cd docker-uptimekuma
   ```

2. **Configure Environment (Optional):**
   The project includes a `.env.example` file. You can create a `.env` file to customize the timezone or port, though the defaults are usually sufficient.
   ```bash
   cp .env.example .env
   ```
   *Note: The `.env` file is ignored by git to protect your secrets.*

3. **Start the Service:**
   Run the following command to start Uptime Kuma in the background:
   ```bash
   docker compose up -d
   ```

4. **Access the Dashboard:**
   Open your browser and navigate to:
   [http://localhost:3001](http://localhost:3001)

## Configuration

- **Data Persistence**: All data (monitors, stats, settings) is stored in the `./data` directory, which is mapped to `/app/data` in the container. This ensures your data survives container restarts.
- **Port**: The service listens on port `3001` by default. You can change the external port in `docker-compose.yml` if needed.
- **Timezone**: Set the `TZ` environment variable in `.env` to your local timezone (e.g., `Asia/Bangkok`, `UTC`) for accurate log timestamps.

## Project Structure

- `docker-compose.yml`: Main service definition.
- `data/`: Directory for persistent SQLite database and uploads.
- `.env.example`: Template for environment variables.
- `scripts/`: Helper scripts (if any).

Copyright © 2026 ryumada. All Rights Reserved.

Licensed under the [MIT](LICENSE) license.
