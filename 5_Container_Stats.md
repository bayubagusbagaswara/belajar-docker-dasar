# Container Stats (Statistik container)

- Saat menjalankan beberapa container di Sistem Host, penggunaan resource seperti CPU dan Memory hanya terlihat yang digunakan oleh Docker saja (tidak spesifik pada container yang berjalan didalam Docker)
- Kadang kita ingin melihat detail dari penggunaan resource untuk tiap container nya
- Untungnya docker memiliki kemampuan untuk melihat penggunaan resource dari tiap container yang sedang berjalan
- Kita bisa menggunakan perintah : `docker container stats`
