# Portainer Stack

Runs Portainer CE with a local Portainer Agent for Docker environment management.

## Services

- `agent` using image `portainer/agent`
- `portainer` using image `portainer/portainer-ce`

## Environment Variables

This stack does not use configurable environment variables in `docker-compose.yml`.

## Notes

- Agent listens on `9001/tcp`.
- Portainer UI/API are exposed on `9443/tcp` and tunnel server on `8000/tcp`.
- Portainer data persists in Docker volume `portainer_data`.