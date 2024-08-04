# How to Use the PHP Docker Image with Composer

This document explains how to use a custom Docker image for PHP with Composer. The PHP version in this image is 8.3.10. Below are the necessary commands to run and interact with the container.

## Running the PHP Container with Composer

To start a Docker container in the background using the `php-composer:1.0` image, use the following command:

    docker run -d --name php-composer php-composer:1.0

To share a volume with the container, add the -v flag:

    docker run -d --name php-composer -v .:/app php-composer:1.0

## Access the Container

To access the running container and get an interactive terminal, use the command:

    docker exec -it php-container sh

## Using the Server Directory

The server directory is located at `/var/www/html`. To use it, run:

    cd /var/www/html

If you are using Laravel, use the `--host` flag to point to the address `0.0.0.0`:
  
    php artisan serve --host=0.0.0.0

To discover the IP address of the container, execute the following command inside the container:

    hostname -I

Written by [Marcelo de Santana](https://github.com/marcelo-de-santana)