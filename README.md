# Tailscale NordVPN Gateway — Home Assistant integration

A custom Home Assistant integration for the **Tailscale NordVPN Exit Gateway** add-on.

It discovers the installed add-on through the Home Assistant Supervisor API and provides:
- Add-on status and NordVPN public-IP sensors
- A NordVPN location selector
- An exit-node advertising switch
- A gateway restart button

## Requirements

- Home Assistant 2026.11.0 or newer
- The separate **Tailscale NordVPN Exit Gateway** add-on installed in the same Home Assistant instance

The integration does not install another Tailscale or VPN instance and does not expose a network port. It uses Home Assistant's built-in Supervisor API.

## Installation

1. Confirm the gateway add-on is installed and running.
2. In Home Assistant, open **Settings → Devices & services → Add integration**.
3. Search for **Tailscale NordVPN Gateway** and complete setup.
4. Add the created entities to a dashboard.

If it is not available in the built-in Marketplace, add this public repository as a custom integration repository in **Settings → Marketplace**:

`https://github.com/dutchtexan25/ha-tailscale-nordvpn-gateway-integration`

## Entities

The integration creates status and public-IP sensors, a NordVPN location select, an advertise-exit-node switch, and a restart button.

Changing the NordVPN location or exit-node setting updates the add-on options and restarts only the gateway add-on. This briefly interrupts clients using this exit node.

## Development status

Initial development release. This integration has not yet been runtime-tested on the target Home Assistant installation. In particular, Supervisor API permissions, add-on option updates, and the optional log-reading route need validation on the user's system.

Issues: https://github.com/dutchtexan25/ha-tailscale-nordvpn-gateway-integration/issues
