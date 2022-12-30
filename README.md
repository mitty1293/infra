# my_reverse_proxy
reverse proxy for my web app integration
## Deploy
```
docker network create traefik_reverse_proxy_network
docker compose up -d
echo $(htpasswd -nb username password) > ./config/.htpasswd
```
## Dashboard
Access to `https://fmitty.net/dashboard/`.
Enter the username and password you set up in `config/.htpasswd`
## Configuration File
* Static Configuration: `config/traefik.yml`
* Dynamic Configuration: `config/dynamic/dynamic_conf.yml`
