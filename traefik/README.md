# Traefik Reverse Proxy

Traefik (pronounced traffic) is a modern HTTP reverse proxy and load balancer that makes deploying microservices easy.

## Test Container

Check the logs

```bash
docker logs traefik
```

Enter the container and check Top

```bash
docker exec -it traefik /bin/sh
```

```bash
top
```

Check volume binds in container

```bash
ls
```

Check environmental variables in the container

```bash
echo ${TRAEFIK_DASHBOARD_CREDENTIALS}
echo ${CF_DNS_API_TOKEN}
```

## References

- [Traefik 3 and FREE Wildcard Certificates with Docker](https://technotim.live/posts/traefik-3-docker-certificates/)