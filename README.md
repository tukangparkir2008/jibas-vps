# jibas-dockercompose
Running JIBAS using docker-compose

## Requirements:
- Docker with docker-compose

## Instalasi:
1. Rename file .env-example ke .env
2. Build Repository aplikasi `docker compose build jibasapp`
3. Jalankan terlebih dahulu MariaDB server `docker compose up -d mysql`
4. Setelah selesai membuild dan menjalankan mariadb lakukan instalasi `docker compose run --rm jibasapp make install`
5. Baru jalankan aplikasi docker `docker compose up -d`

## Menjalankan
1. `docker-compose up -d`
2. Buka di browser http://localhost:3001/jibas/
