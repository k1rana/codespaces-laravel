FROM mcr.microsoft.com/devcontainers/php:1-8.3-bullseye

RUN apt-get update \
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y mariadb-client \ 
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libzip-dev \
    unzip \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

# Install php-mysql driver
RUN docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd zip bcmath mysqli pdo pdo_mysql