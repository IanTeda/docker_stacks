# Cloudflared Zero Trust Tunnels

Cloudflare zero trust tunnels can be used without having to open up ports on your firewall.

## Cloudflared Token

On creating a new tunnel a clodflare provide a token that should be added to the `CLOUDFLARED_TUNNEL_TOKEN` variable in .env

```properties
CLOUDFLARED_VERSION=AddVersionIfYoudoNotWantLatest
CLOUDFLARED_TUNNEL_TOKEN=ReplaceWithZeroTrustTunnelToken
```

## Accessing the tunnel from docker-compose outside of this one

Add the Cloudflared tunnel network to your docker compose file

```dockerfile
networks:
  default: # this docker-compose network
    driver: bridge
  cloudflared_tunnel_network: # Cloudflare zero trust tunnel network
    external: true

services:
  app:
    networks:
      - cloudflared_tunnel_network
 ...

```