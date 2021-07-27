FROM php:7.4-cli

WORKDIR /var/www

# Update
RUN apt-get update

# Instalar zip
RUN apt-get install libzip-dev -y && \
    docker-php-ext-install zip

# Instalar composer (repositório semelhante ao Maven)
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php composer-setup.php && \
    php -r "unlink('composer-setup.php');"

# Instalar Laravel
RUN php composer.phar create-project --prefer-dist laravel/laravel laravel

# Executar comando ao início do container
ENTRYPOINT [ "php","laravel/artisan","serve" ]

# Comando padrão caso argumento não seja passado
CMD [ "--host=0.0.0.0" ]