# Belajar Docker Dasar

# Virtual Machine

- Dalam dunia Infrastructure, kita sudah terbiasa dengan yang namanaya VM (Virtual Machine)
- Saat membuat sebuah VM, biasanya kita akan menginstall sistem operasi nya juga di VM tersebut
- Masalahnya ketika kita menggunakan VM adalah proses yang lambat ketika membuat VM nya. Dan butuh waktu untuk boot sistem operasi di dalam VM tersebut ketika kita menjalankan VM atau me-restart VM tersebut.

# Hypervisor

- adalah Virtual Machine Manager
- contohnya VMware
- VM itu berjalan diatas Hypervisor

# Container

- Berbeda dengan VM, Container sendiri `berfokus pada sisi aplikasi`
- Container sendiri sebenarnya `berjalan diatas aplikasi Container Manager`
- Container Manager sendiri berjalan di sistem operasi.
- Yang membedakan dengan VM adalah :
  - Pada Container, kita bisa `mem-package aplikasi dan dependency-nya tanpa harus menggabungkan sistem operasi`
- Container akan `menggunakan sistem operasi host dimana Container Manager nya berjalan`. Oleh karena itu, Container akan lebih hemat resource dan lebih cepat jalannya, karena tidak butuh sistem operasi sendiri.
- Ukuran Container biasanya hanya hitungan MB, berbeda dengan VM yang bisa sampai GB karena di dalamnya ada sistem operasinya

# Pengenalan Docker

- Docker adalah salah satu implementasi Container Manager (aplikasi yang digunakan untuk me-manage container) yang saat ini paling populer.
- Docker merupakan teknologi yang masih baru, karena baru diperkenalkan sekitar tahun 2013
- Docker adalah aplikasi yang free dan Open Source, sehingga bisa kita gunakan secara bebas

# Docker Architecture

- Docker menggunakan arsitektur Client-Server
- Docker client berkomunikasi dengan Docker Daemon (server)
- Saat kita menginstall Docker, biasanya didalamnya sudah terdapat Docker Client dan Docker Daemon
- Docker Client dan Docker Daemon bisa berjalan di satu sistem operasi yang sama
- Docker Client dan Docker Daemon berkomunikasi menggunakan REST API

# Mengecek Docker

- Untuk mengecek apakah Docker Daemon sudah berjalan, kita bisa gunakan perintah : `docker version`

# Docker Registry

- Docker Registry adalah `tempat kita menyimpan Docker Image`
- Dengan menggunakan Docker Registry, kita bisa menyimpan Image yang kita buat, dan bisa digunakan di Docker Daemon dimanapun `selama bisa terkoneksi` ke Docker Registry
- misal di cloud kita install Docker, maka docker yang ada di cloud tinggal mengambil image dari docker registry

## Contoh Docker Registry

- Docker Hub
- Digital Ocean Container Registry
- Google Cloud Container Registry
- Amazon Elastic Container Registry
- Azure Container Registry

# Docker Image

- Docker Image mirip seperti installer aplikasi, dimana di dalam Docker Image terdapat aplikasi dan dependency
- Sebelum kita bisa menjalankan aplikasi di Docker, kita perlu memastikan memiliki Docker Image aplikasi tersebut

# Melihat Docker Image

- Docker Image akan di download, lalu disimpan kedalam server nya
- Untuk melihat Docker Image yang terdapat di dalam Docker Daemon, kita bisa menggunakan `docker image ls`

# Download Docker Image

- Untuk download Docker Image dari Docker Registry, kita bisa gunakan perintah: `docker image pull nameimage:tag`
- Kita bisa mencari Docker Image yang ingin kita download di https://hub.docker.com/
- contoh : docker image pull redis:latest

# Menghapus Docker Image

- Perintah : `docker image rm namaimage:tag`

# Docker Container

- Setelah kita buat docker container nya, maka kita tidak bisa menghapus docker image nya. Dikarenanakan sebenarnya Docker Container tidak meng-copy isi Docker Image, tapi hanya menggunakan isinya saja

# Status Container

- Saat kita membuat container, secara default container tersebut tidak akan berjalan
- Mirip seperti kita menginstall aplikasi. Jika tidak kita jalankan, maka aplikasi tersebut tidak akan berjalan, begitu juga container
- Oleh karena itu, setelah membuat container kita perlu menjalankannya jika memang ingin menjalankan container nya

# Melihat Container

- Untuk melihat semua container, baik yang sedang berjalan atau tidak di Docker Daemon, kita bisa gunakan perintah: `docker container ls -a`
- Sedangkan jika kita ingin melihat container yang `sedang berjalan saja`, kita bisa gunakan perintah : `docker container ls`

# Membuat Container

- Untuk membuat container, kita bisa gunakan perintah : `docker container create --name namacontainer namaimage:tag`
- Contoh: `docker container create --name contohredis redis:lates`

# Menjalankan Container

- Untuk menjalankan container yang sudah kita buat, kita busa gunakan perintah: `docker container start containerId/namacontainer`
- contoh running container dengan menggunakan nama container : `docker container start contohredis`

# Menghentikan Container

- Sebelum menghapus sebuah container, maka kita perlu dahulu menghentikan container yang berjalan.
- Untuk menghentikan container, kita bisa gunakan perintah : `docker container stop containerId/namacontainer`
- contoh stop container dengan menggunakan nama container : `docker container stop contohredis`

# Menghapus Container

- Untuk menghapus container yang sudah berhenti, kita bisa menggunakan perintah : `docker container rm containerId/namacontainer`
