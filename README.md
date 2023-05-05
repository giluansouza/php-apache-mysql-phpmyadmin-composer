# php-apache-mysql-phpmyadmin-composer

Docker running Apache, PHP, Composer, MySQL and PHPMyAdmin.

## Overview

1. [Configuração inicial](#initial-config)

    Altere o arquivo .env com os dados do seu container

2. [Gerando certificado SSL](#certificate)

    ```sh
    docker compose up -d
    ```

3. [Run the application](#run-application)

    ```sh
    $ openssl req -x509 -sha256 -newkey rsa:2048 -keyout cert.key -out cert.crt -days 365 -nodes
    ```

4. Open your favorite browser

    * [http://localhost:8005](http://localhost:8005/)
    * [https://localhost:443](https://localhost:443/) ([HTTPS](#configure-apache-with-ssl-certificates) not configured by default)
    * [http://localhost:8080](http://localhost:8080/) PHPMyAdmin (username: root, password: root)
    
5. Stop and clear services

    ```sh
    docker-compose down -v
    ```
