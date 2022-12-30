# my_reverse_proxy
reverse proxy for my web app integration
## Deploy
### Replace the value of HOSTNAME with the hostname of your dashboard
```
cp .env_example .env
vi .env
# Replace the value of HOSTNAME
```
### Start container
```
docker network create traefik_reverse_proxy_network
docker compose up -d
echo $(htpasswd -nb username password) > ./config/.htpasswd
```
## Dashboard
Access to `https://<HOSTNAME>/dashboard/`.  
Enter the username and password you set up in `config/.htpasswd`
## Configuration File
* Static Configuration: `config/traefik.yml`
* Dynamic Configuration: `compose.yml` -> `labels`
