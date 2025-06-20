# n8n Docker Compose Setup

This repository contains a Docker Compose configuration to set up n8n with a PostgreSQL database.

## Prerequisites

- Docker installed on your machine
- Docker Compose installed

## Setup Instructions

1. Clone this repository or copy the `docker-compose.yml` file to your project directory.

2. Create the required Docker volumes for persistent storage:

   ```bash
   docker volume create postgres_data
   docker volume create n8n_data
   ```

3. Start the services using Docker Compose:

   ```bash
   docker-compose up -d
   ```

   This will start the n8n and PostgreSQL containers in detached mode.

4. Access n8n:

   Open your browser and navigate to `http://localhost:5678`. Use the following credentials to log in:

   - **Username:** `user`
   - **Password:** `password`

## Environment Variables

The following environment variables are configured in the `docker-compose.yml` file:

- `N8N_BASIC_AUTH_ACTIVE`: Enables basic authentication for n8n.
- `N8N_BASIC_AUTH_USER`: Username for authentication.
- `N8N_BASIC_AUTH_PASSWORD`: Password for authentication.
- `N8N_HOST`: Hostname for n8n.
- `N8N_PORT`: Port for n8n.
- `N8N_PROTOCOL`: Protocol for n8n (http).
- `DB_TYPE`: Database type (PostgreSQL).
- `DB_POSTGRESDB_HOST`: Hostname for the PostgreSQL database.
- `DB_POSTGRESDB_PORT`: Port for the PostgreSQL database.
- `DB_POSTGRESDB_DATABASE`: Database name.
- `DB_POSTGRESDB_USER`: Database username.
- `DB_POSTGRESDB_PASSWORD`: Database password.

## Volumes

- `postgres_data`: Stores PostgreSQL data.
- `n8n_data`: Stores n8n data.

## Stopping the Services

To stop the services, run:

```bash
docker-compose down
```

## Viewing Logs

To follow the logs of the n8n container, run:

```bash
docker-compose logs -f n8n
```

## License

This project is licensed under the MIT License.
