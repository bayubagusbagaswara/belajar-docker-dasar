# Container Environment Variable

- Saat membuat aplikasi, menggunakan Environment Variable adalah salah satu teknik agar konfigurasi aplikasi bisa diubah secara dinamis
- Dengan menggunakan environment variable, kita bisa mengubah-ubah konfigurasi aplikasi, tanpa harus mengubah kode aplikasinya lagi
- Docker Container memiliki parameter yang bisa kita gunakan untuk mengirim environment variable ke aplikasi yang terdapat di dalam container

# Menambah Environment Variable

- Untuk menambah environment variable, kita bisa menggunakan perintah `--env` atau `-e`. Misal : `docker container create --namecontainer --env KEY="value" --env KEY2="value" image:tag`
- contoh : kita akan create container untuk database mongodb. Perintahnya : `docker container create --name contohmongo --publish 27017:27017 --env MONGO_INITDB_ROOT_USERNAME=bayu --env MONGO_INITDB_ROOT_PASSWORD=bayu mongo:latest`

- download dulu image untuk database mongodb

```sh
docker image pull mongo:latest
```

- buat container nya

```sh
docker container create --name contohmongo --publish 27017:27017 --env MONGO_INITDB_ROOT_USERNAME=bayu --env MONGO_INITDB_ROOT_PASSWORD=bayu mongo:latest
```

- lalu kita coba jalankan container mongo nya

```sh
docker container start contohmongo
```

- Kalau kita coba akses mongodb dengan menggunakan database client mongo, misalnya Robo Mongo, maka kita cukup memasukkan usernmae dan password sesuai dengan settingan envi pada container nya, dan juga sesuaikan port nya. Karena tadi portnya 0.0.0.0:27017, maka kita cukup masukkan localhost saja

- jika container mongo dimatikan, maka database client tidak bisa mengakses database mongo nya
