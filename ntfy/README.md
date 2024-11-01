# Ntfy

A simple HTTP-based pub-sub notification service.

## Add admin user to Ntfy

```bash
docker exec -it ntfy sh
```

```bash
ntfy user add --role=admin <username>
```

## Check Working

```bash
curl -d "Hi" https://<FQDN_NTFY>/<subscription> -u :<access_token>
```

## References

* [binwiederhier/ntfy](https://github.com/binwiederhier/ntfy)
* [Setup ntfy for selfhosted notifications with Cloudflare Tunnel](https://medium.com/@svenvanginkel/setup-ntfy-for-selfhosted-notifications-with-cloudflare-tunnel-e342f470177d)