# Gunakan image dasar PHP 8.3 FPM
FROM php:8.3-fpm

# Set working directory
WORKDIR /app

# Instal dependensi sistem yang dibutuhkan
# Termasuk: git, curl, wget (untuk unduhan)
#           Dependensi untuk ekstensi PHP (libpng, libjpeg, libfreetype, libzip, libonig, libcurl, libxml2, libsqlite3, libmagic)
#           pkg-config (alat bantu build)
#           gettext (untuk ekstensi gettext)
#           zip, unzip (utilitas arsip umum)
#           ca-certificates (untuk manajemen sertifikat SSL)
#           p7zip-full (untuk ekstraksi arsip .7z) <-- SUDAH ADA DI SINI
#           mariadb-client (untuk interaksi dengan database MariaDB)
RUN apt-get update && apt-get install -y --no-install-recommends \
    git \
    curl \
    wget \
    libpng-dev \
    libjpeg-dev \
    libfreetype6-dev \
    libzip-dev \
    libonig-dev \
    libcurl4-openssl-dev \
    libxml2-dev \
    libsqlite3-dev \
    libmagic-dev \
    pkg-config \
    gettext \
    zip \
    unzip \
    ca-certificates \
    p7zip-full \
    mariadb-client \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* \
  && update-ca-certificates # Perbarui trust store CA setelah instalasi ca-certificates

# Konfigurasi dan instal ekstensi GD (memerlukan perhatian khusus)
RUN docker-php-ext-configure gd --with-freetype --with-jpeg \
  && docker-php-ext-install -j$(nproc) gd

# Instal ekstensi PHP lainnya satu per satu untuk memudahkan debugging jika ada error
RUN docker-php-ext-install fileinfo
RUN docker-php-ext-install curl
RUN docker-php-ext-install gettext
RUN docker-php-ext-install mbstring
RUN docker-php-ext-install exif
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install pdo_sqlite
RUN docker-php-ext-install zip

# Salin file konfigurasi PHP kustom (jika ada)
# Pastikan file custom-php.ini ada di direktori yang sama dengan Dockerfile ini (./images/php/)
# File ini akan berisi setting seperti short_open_tag, error_reporting, dll.
COPY custom-php.ini /usr/local/etc/php/conf.d/zz-custom-php.ini

# CMD default untuk menjalankan PHP-FPM
CMD ["php-fpm"]
