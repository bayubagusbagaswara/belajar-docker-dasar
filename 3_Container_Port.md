# Container Port

- Saat menjalankan container, container tersebut terisolasi di dalam Docker
- Artinya sistem Host (misal Laptop kita), tidak bisa mengakses aplikasi yang ada di dalam container secara langsung. Salah satu caranya adalah dengan harus menggunakan Container Exec untuk masuk ke dalam container nya.
- Biasanya sebuah aplikasi berjalan pada port tertentu. Misal saat kita menjalankan aplikasi Redis, dia berjalan pada port 6379 (port didalam container nya), kita bisa melihat port apa yang digunakan ketika melihat semua daftar container

# Port Forwarding

- Docker memiliki kemampuan untuk melakukan port forwading, yaitu meneruskan sebuah port yang terdapat di sistem Host nya ke dalam Docker Container
- Cara ini cocok jika kita ingin mengekspos port yang terdapat di container ke luar melalui sistem Host nya

# Melakukan Port Forwading

- Untuk melakukan post forwading, kita bisa menggunakan perintah berikut ketika membuat container nya: `docker container create --name namacontainer --publish posthost:portcontainer image:tag`
- Jika kita ingin melakukan port forwading lebih dari satu, kita bisa tambahkan dua kali parameter `--publish`
- `--publish` juga bisa disingkat menggunakan `-p`
