# php-apache-mysql-phpmyadmin-composer

Docker running Apache, PHP, Composer, MySQL and PHPMyAdmin.

## Overview

1. [Initial Config](#initial-config)

    Change the file .env with your container data

2. [Generating SSL Certificate](#certificate)

    ```sh
    openssl req -x509 -sha256 -newkey rsa:2048 -keyout .docker/php-apache/apache-ssl/cert.key -out .docker/php-apache/apache-ssl/cert.crt -days 365 -nodes
    ```

3. [Run the application](#run-application)

    ```sh
    docker compose up -d
    ```

4. Open your favorite browser

    * [http://localhost:8005](http://localhost:8005/)
    * [https://localhost:443](https://localhost:443/) ([HTTPS](#configure-apache-with-ssl-certificates) not configured by default)
    * [http://localhost:8080](http://localhost:8080/) PHPMyAdmin (username: root, password: root)
    
5. Stop and clear services

    ```sh
    docker-compose down -v
    ```
___

## Use Docker commands

### Installing package with composer

```sh
docker run --rm -v $(pwd)/webapp:/app composer install
```

### Require package with composer

```sh
docker run --rm -v $(pwd)/webapp:/app composer require league/plates
```

### Updating PHP dependencies with composer

```sh
docker run --rm -v $(pwd)/webapp:/app composer update
```
