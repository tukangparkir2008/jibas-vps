# jibas-dockercompose
Running JIBAS using docker-compose

## Requirements:
- Docker with docker-compose

## Instalasi:
1. Download [JIBAS Education Commonity](http://www.jibas.net/content/download/download.php)
2. Extract ke dalam direktori ./app
3. Jalankan database: `docker-compose up -d mysql`
4. Import file SQL
5. Jalankan aplikasi: `docker-compose up nginx jibasapp`
6. Buka di browser ke: http://localhost:8080/jibas/
