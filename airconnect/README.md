# AirConnect Stack

Runs AirConnect to expose AirPlay and Chromecast compatibility bridges on your local network.

## Services

- `airconnect` using image `1activegeek/airconnect`

## Environment Variables

The stack uses container arguments passed via environment variables and does not require user-supplied values.

| Variable | Value | Purpose |
| --- | --- | --- |
| `AIRCAST_VAR` | `-x /config/config.xml` | Tells AirCast to use the XML config file in `/config`. |
| `AIRUPNP_VAR` | `kill` | Disables the AirUPnP process in this container. |

## Notes

- Uses `network_mode: host`, so service discovery works across your LAN.
- Persists config in Docker volume `airconnect_config`.