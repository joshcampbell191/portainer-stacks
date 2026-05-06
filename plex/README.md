# Plex Stack

Runs Plex Media Server with hardware transcoding devices mapped from the host.

## Services

- `plex` using image `plexinc/pms-docker`

## Environment Variables

Set these values in Portainer stack variables or an `.env` file before deployment.

| Variable | Required | Example | Purpose |
| --- | --- | --- | --- |
| `PLEX_UID` | Yes | `1026` | Host user ID Plex runs as for file permissions. |
| `PLEX_GID` | Yes | `100` | Host group ID Plex runs as for file permissions. |
| `IP_PLEX` | Yes | `192.168.1.54` | Static IP assigned to Plex on the external `macvlan` network. |

## Fixed Environment Values

| Variable | Value |
| --- | --- |
| `TZ` | `Canada/Eastern` |

## Notes

- Requires an existing external Docker network named `macvlan`.
- Maps host media path `/volume1/media` to container path `/data` (read-only).
- Persists config and transcode data in `plex_config` and `plex_transcode` volumes.