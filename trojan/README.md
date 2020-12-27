# trojan with caddy2

## Steps

- (REQUIRED) Update [`env`](env)
  - set `SRV_HOSTNAME` to your server domain name
  - set `REDIRECT_TO` to a server handling non-trojan traffic redirect (caddy reverse-proxy)
  - set `ACME_EMAIL` to your email for letsencrypt certs
- (REQUIERD) Update [`trojan-server.yaml`](trojan-server.yaml)
  - Update `password` for users
- (OPTIONAL) Update [`Caddyfile`](Caddyfile) if you do not want to to use reverse proxy
- (OPTIONAL) Update [`docker-compose.yml`](docker-compose.yml) for certificate testing
  - set `ACME_CA_DIRECTORY_URL` to `https://acme-staging-v02.api.letsencrypt.org/directory` for testing
    - and you should update volume mount from `/opt/caddy/certificates/acme-v02.api.letsencrypt.org-directory/` to `/opt/caddy/certificates/acme-staging-v02.api.letsencrypt.org-directory/`
- Run `docker-compose up -d` (also applicable to `podman-compose`)
