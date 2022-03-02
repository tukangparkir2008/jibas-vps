# jibas-dockercompose
Running JIBAS using docker-compose

## Requirements:
- Docker with docker-compose

## Instalasi:
1. Clone repository ini `git clone https://github.com/ivanp/jibas-dockercompose.git`
2. Masuk ke direktori `cd jibas-dockercompose`
3. Copy file .env-example ke .env
4. Jalankan MariaDB server `docker-compose up mysql`
5. Buka terminal baru jalakan script instalasi `docker-compose run --rm jibasapp make install`

## Menjalankan
1. `docker-compose up`
2. Buka di browser http://localhost:3001/jibas/