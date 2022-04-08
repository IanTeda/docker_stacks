# Nextcloud Docker Compose

Environmental variables need to be set in `.env`. An example config can be found at `env.example`.

## Redis

To use Redis `/config/www/nextcloud/config/config.php needs to be updated to include:

```php
'redis' => [
    'host' => 'redis',
    'port' => 6379,
],
'memcache.locking' => '\OC\Memcache\Redis',
```

## Reverse Proxy

To use a reverse proxy you domain needs to be added as a trusted_domain in `/config/www/nextcloud/config/config.php

```php
'trusted_domains' =>
[
    'nas.local:3443',
    'nextcloud.domain.com'
],
```
