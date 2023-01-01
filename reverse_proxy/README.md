# reverse_proxy
reverse proxy for my web app integration
## Deploy
1. Replace the value of HOSTNAME with the hostname of your dashboard.
    ```
    # Copy .env_example as .env
    cp .env_example .env
    vi .env
    ```
    ```
    # Replace the value of HOSTNAME in .env
    HOSTNAME=example.com
    ```
2. Replace the email address used for registration in `config/traefik.yml`.
    ```
    # config/traefik.yml
    certificatesResolvers:
        myresolver:
            acme:
                email: your-email@example.com
    ```
3. To add basic authentication to the dashboard, prepare a file(`/config/.htpasswd`) containing the user name and password.
    ```
    echo $(htpasswd -nb username password) > ./config/.htpasswd
    ```
4. Start container.
    ```
    docker network create traefik_reverse_proxy_network
    docker compose up -d
    ```
## Dashboard
Access to `https://<HOSTNAME>/dashboard/`.  
Enter the username and password you set up in `config/.htpasswd`
## Configuration File
* Static Configuration: `config/traefik.yml`
* Dynamic Configuration: `compose.yml` -> `labels`
