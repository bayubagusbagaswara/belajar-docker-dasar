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

- Docker Registry adalah tempat kita menyimpan Docker Image
- Dengan menggunakan Docker Registry, kita bisa menyimpan Image yang kita buat, dan bisa digunakan di Docker Daemon dimanapun selama bisa terkoneksi ke Docker Registry
