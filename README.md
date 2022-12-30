# my_reverse_proxy
reverse proxy for my web app integration
## Deploy
### Replace the value of HOST with the hostname of your dashboard
```
# config/dynamic/dynamic_conf.yml
http:
  routers:
    dashboard:
      rule: Host(`example.com`) && (PathPrefix(`/api`) || PathPrefix(`/dashboard`))
      # Replace the value of HOST
```
### Start container
```
docker network create traefik_reverse_proxy_network
docker compose up -d
echo $(htpasswd -nb username password) > ./config/.htpasswd
```
## Dashboard
Access to `https://<HOST>/dashboard/`.  
Enter the username and password you set up in `config/.htpasswd`
## Configuration File
* Static Configuration: `config/traefik.yml`
* Dynamic Configuration: `config/dynamic/dynamic_conf.yml`
