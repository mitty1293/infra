# my_reverse_proxy
reverse proxy for my web app integration
## Deploy
```
docker network create traefik_reverse_proxy_network
docker compose up -d
echo $(htpasswd -nb username password) > ./config/.htpasswd
```
## Dashboard
Access to `https://reverse-proxy-dashboard.fmitty.net/dashboard/`
