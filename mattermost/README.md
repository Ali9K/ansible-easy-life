# Ansible Role: Deploy Mattermost with PostgreSQL using Docker

This Ansible role automates the deployment of the [Mattermost](https://mattermost.com/) messaging platform along with a PostgreSQL database using Docker and Docker Compose.

## What This Role Does

- Ensures **Docker** and **Docker Compose** are installed on the target host.
- Creates necessary directories for Mattermost deployment.
- Copies the provided `docker-compose.yml` and `.env` files to the target host.
- Runs the Mattermost stack via `docker-compose`.

## License
- MIT
