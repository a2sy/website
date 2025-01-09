+++
authors = ["Arif"]
title = "Panduan Termux untuk pemula 101"
description = "Panduan untuk mulai menggunakan Termux, emulator terminal linux open-source untuk perangkat Android."
date = 2025-01-08
draft = false
[taxonomies]
tags = ["command-line", "termux", "android", "linux"]
[extra]
toc = true
+++

{{ image(url="neofetch_termux.png", alt="run neofetch on termux" no_hover=true) }}

# Termux
Termux adalah emulator terminal *open-source* untuk perangkat android, termux memungkinkan untuk menjalankan berbagai perintah dan program Linux langsung dari perangkat android tanpa perlu melakukan *root*.

# Mengapa Menggunakan Termux?
Ada banyak alasan mengapa termux menjadi populer dan banyak digunakan oleh orang
1. Termux bekerja tanpa memerlukan akses *root*. Ini penting karena *root* dapat membatalkan garansi perangkat Anda dan berpotensi menimbulkan masalah keamanan.
2. Termux menyediakan lingkungan Linux yang lengkap dengan berbagai *tool* dan utilitas, seperti Bash, Zsh, Vim, Nano, Git, dan banyak lagi. Anda dapat menginstal berbagai paket perangkat lunak yang tersedia di repositori Termux. Contohnya, Anda bisa menginstal `neovim` sebagai teks editor, atau `neofetch` untuk menampilkan informasi sistem dengan tampilan yang menarik.
3. Akses Jarak Jauh (Remote Access) komputer lain melalui SSH. Misalnya, Anda dapat menggunakan Termux untuk mengelola server web Anda atau mengakses komputer pribadi Anda dari jarak jauh.

# Unduh Termux
Disarankan untuk tidak mengunduh termux melalui google playstore, termux dapat diunduh langsung melalui melalui [github](https://github.com/termux/termux-app/releases)atau [F-Droid](https://f-droid.org/en/packages/com.termux/).


{{ image(url="download_termux_github.png", alt="download termux github" no_hover=true) }}

{{ image(url="download_termux_fdroid.png", alt="download termux on f-droid" no_hover=true) }}

# Hal yang dapat dilakukan setelah memasang Termux
{{ image(url="homescreen_termux.png", alt="termux homescreen" no_hover=true) }}

Ada beberapa hal yang mungkin dibutuhkan setelah memasang Termux, beberapa diantaranya yaitu: 

## Memperbarui repositori dan packages
Perintah ini akan memperbarui daftar packages dari repositori Termux
```bash
pkg update
```
Kemudian jalankan perintah berikut untuk upgrade packages yang sudah terpasang ke versi terbaru
```bash
pkg upgrade -y
```
Opsi -y secara otomatis menjawab "yes" untuk semua pertanyaan konfirmasi, sehingga proses upgrade berjalan tanpa interupsi.

{{ image(url="update_upgrade_termux.png", alt="update upgrade termux" no_hover=true) }}

## Memasang packages pada Termux
Untuk memasang packages (software) pada termux, cukup mengetik `pkg install <nama-packages>` pada terminal termux

Contoh, untuk memasang `neofetch`, ketikkan:
```bash
pkg install neofetch
```

Untuk menghapus `neofetch`, ketikkan:
```bash
pkg remove neofetch
```

Untuk mencari nama packages di repository termux, gunakan:
```bash
pkg search <nama-packages>
```

## Memberikan izin akses ke penyimpanan 
Secara default, Termux memiliki akses terbatas ke penyimpanan internal. Untuk memberikan akses penuh, jalankan perintah berikut:
```
termux-setup-storage
```
Ini akan meminta izin akses penyimpanan. Setelah diberikan, Anda dapat mengakses penyimpanan internal melalui direktori /storage.

## Melakukan remote access ke komputer lain dengan SSH
Secara default SSH belum terpasang di Termux, untuk melakukan remote access dengan SSH perlu untuk memasang packages `openssh` terlebih dahulu
```bash
pkg install openssh
```

setelah `openssh` berhasil terpasang, sekarang Anda sudah bisa terhubung dengan komputer lain dengan SSH
```bash
ssh -p 22 <username>@<host/ip_address>
```

# Perintah Dasar Termux
Berikut beberapa perintah dasar yang perlu diketahui untuk berinteraksi dengan Termux
- `pkg update` atau `apt update`: Memperbarui daftar packages yang tersedia
- `pkg upgrade` atau `apt upgrade`: Mengupgrade packages yang sudah terpasang ke versi terbaru
- `ls`: Menampilkan daftar file dan direktori di direktori saat ini
- `cd <direktori>`: Berpindah ke direktori lain, Contoh: `cd /storage` untuk berpindah ke penyimpanan internal.
- `cd ..`: Kembali ke direktori sebelumnya
- `pwd`: Menampilkan lokasi direktori saat ini
- `mkdir <nama-direktori>`: Membuat direktori baru
- `rm <nama-file>`: Menghapus file
- `rmdir <nama-direktori>`: Menghapus direktori
- `clear`: Membersihkan layar terminal
- `exit`: Keluar dari termux

# Referensi dan bacaan menarik
- <a class="external" href="https://ivonblog.com/en-us/posts/how-to-use-termux/" target="_blank">A simple Termux tutorial for beginners - Ivon's Blog</a> <br>
- <a class="external" href="https://wiki.termux.com/wiki/" target="_blank">Termux Wiki</a> <br>
- <a class="external" href="https://github.com/termux/termux-app" target="_blank">Termux Github Repository</a> <br>