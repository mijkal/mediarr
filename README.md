# mediarr

### Get started

##### Volume mounts
- Update `docker-compose.yaml` volume mount paths to match your persistent docker app service data/configs and media library

##### VPN setup
- Update your vpn env for **gluetun** service in `docker-compose.yaml`:
  - Wireguard config is entirely in `vpn.env`
  - OpenVPN mounts a directory at /gluetun containing:
    `client.crt` `client.key` `servers.json`
_My current VPN seems to be more reliable with OpenVPN; ymmv_
https://github.com/qdm12/gluetun-wiki/blob/main/setup/providers/airvpn.md

##### Link apps
- The only tedious part of this is initial setup:
  -   Apps are linked with API keys randomly generated in each service (see gluetun service for mapped ports for each app)
  - In qbit config, set the port to match your VPN port (setup with your VPN provider)
  - [Visual setup guide (YouTube)](https://youtu.be/3k_MwE0Z3CE?si=ZR8Q0nSmCc81OIN4&t=741)
  - [Lots of how-to guides out there (Google)](https://www.google.com/search?q=sonarr+radarr+arr+setup&client=safari&sca_esv=839bd3d9177a184d&sca_upv=1&rls=en&sxsrf=ADLYWIIcCxELxnDGASBB9GYi_2GSuuQqcQ%3A1715455377072&ei=kcU_ZvT4A5Ki0PEP-cm60Ao&ved=0ahUKEwi0hYOjqYaGAxUSETQIHfmkDqoQ4dUDCA8&uact=5&oq=sonarr+radarr+arr+setup&gs_lp=Egxnd3Mtd2l6LXNlcnAaAhgCIhdzb25hcnIgcmFkYXJyIGFyciBzZXR1cDIIECEYoAEYwwRI-BtQ-w1YvRZwAngBkAEAmAFtoAGgA6oBAzEuM7gBA8gBAPgBAZgCBqACuAPCAgoQABiwAxjWBBhHwgINEAAYgAQYsAMYQxiKBcICChAjGIAEGCcYigXCAgYQABgHGB7CAgYQABgFGB7CAgsQABiABBiGAxiKBcICCBAAGAcYCBgewgILEAAYgAQYogQYiwPCAggQABiABBiiBJgDAIgGAZAGCpIHAzIuNKAH8RA&sclient=gws-wiz-serp)

#### Nice follow-ups
- Setup local dns and reverse proxy to navigate to **$service.lan**
- Setup VPN server to get back to your network from anywhere (and/or use Tailscale)
