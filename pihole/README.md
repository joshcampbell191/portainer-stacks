# Pi-hole Stack

Runs Pi-hole for DNS filtering and ad blocking on a dedicated LAN IP via an external `macvlan` network.

## Services

- `pihole` using image `pihole/pihole`

## Environment Variables

Set these values in Portainer stack variables or an `.env` file before deployment.

| Variable | Required | Example | Purpose |
| --- | --- | --- | --- |
| `FTLCONF_dns_revServers` | Yes | `true,192.168.1.0/24,192.168.1.1,local` | Enables/configures conditional reverse DNS. |
| `FTLCONF_dns_upstreams` | Yes | `1.1.1.1;1.0.0.1` | Upstream DNS resolvers used by Pi-hole. |
| `FTLCONF_webserver_api_password` | Yes | `change-me` | Sets the Pi-hole web/API admin password. |
| `IP_PIHOLE` | Yes | `192.168.1.53` | Static IP assigned to Pi-hole on the external `macvlan` network. |

## Fixed Environment Values

| Variable | Value |
| --- | --- |
| `TZ` | `Canada/Eastern` |

## Notes

- Requires an existing external Docker network named `macvlan`.
- Persists Pi-hole data in Docker volume `pihole_pihole`.