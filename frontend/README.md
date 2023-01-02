# frontend
各Webアプリへのリンクを表示するトップページ
## Deploy
1. Replace the value of DOMAIN with the domain.
    ```
    # Copy .env_example as .env
    cp .env_example .env
    vi .env
    ```
    ```
    # Replace the value of DOMAIN in .env
    DOMAIN=example.com
    ```
2. Start container.
    ```
    docker compose up -d
    ```
3. Access to `https://<DOMAIN>`