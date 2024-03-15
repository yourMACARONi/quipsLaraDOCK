# Use a base image with PHP already installed
FROM php:8.2.11-fpm

# Install Composer
RUN echo "\e[1;33mInstall COMPOSER\e[0m" && \
    cd /tmp && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install PDO and PDO MySQL extensions
RUN docker-php-ext-install pdo pdo_mysql

# Update packages and install additional tools and libraries
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    apt-utils \
    nano \
    git \
    curl \
    libcurl4-openssl-dev \
    libssl-dev \
    zlib1g-dev \
    zip \
    libbz2-dev \
    locales \
    libmcrypt-dev \
    libicu-dev \
    libonig-dev \
    libxml2-dev \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Set the locale
RUN echo "en_US.UTF-8 UTF-8" > /etc/locale.gen && \
    locale-gen
