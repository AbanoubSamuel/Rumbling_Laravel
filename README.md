# Laravel 10 

The goal of this project is to serve as a boilerplate for Laravel 10
utilizing light-weight alpine linux images for nginx and php 8.2 (fpm).

Stack:

- app @ php:8.2-fpm-alpine
- nginx @ nginx:alpine
- mysql @ mysql
- redis @ redis:alpine
- worker-local @ php:8.2-alpine3.16

## TODO

- add a basic, highly optional seeder for user
- hook up worker-local so you have a queue to play with
- create an example job/worker you might co-locate on same hardware
- maybe add some ci/cd and even k8s stuff as an example to scale out workers/nginx/edges

## Notes

- docker/app docker/nginx will rely on supervisor to maintain their processes, yawn
- Please see .env "#PORT FORWARDS" before starting in docker-compose
-

## Installation

The default docker-compose config here exposes ports if you want them.  See .env's "PORT FORWARDS"

# Rumbling Games Studio Laravel

Brief description of the project.

## Prerequisites

- PHP 8.2 or higher
- Laravel 10
- MySQL database
- Postman (for testing APIs)

## Installation

1. Clone the repository:

   ```bash
    git clone https://github.com/AbanoubSamuel/Rumbling_Laravel.git
   
    cd Rumbling_Laravel

    composer install

You can now access http://localhost:8022 (or whatever your FORWARD_NGINX_PORT is).

Please keep ./composer.lock in docker/app container context, for example:

```shell
docker-compose exec -u root app /bin/sh
# then...
# COMPOSER_MEMORY_LIMIT=-1 app composer install
# COMPOSER_MEMORY_LIMIT=-1 app composer require awesome/package_etc
# ymmv w/ COMPOSER_MEMORY_LIMIT maybe try without
```
