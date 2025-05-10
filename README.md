# jibas-dockercompose
Running JIBAS using docker compose

## Requirements:
- Docker with docker compose

## Instalasi:
1. Rename file .env-example ke .env
2. Build Repository aplikasi `docker compose build jibasapp`
3. Jalankan terlebih dahulu MariaDB server `docker compose up -d mysql`
4. Setelah selesai membuild dan menjalankan mariadb lakukan instalasi `docker compose run --rm jibasapp make install`
5. Baru jalankan aplikasi docker `docker compose up -d`

## Jika sudah di build sebelumnya
1. `docker compose build --no-cache jibasapp`
2. Buka di browser http://localhost:3001/jibas/
