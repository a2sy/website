+++
authors = ["Arif"]
title = "Terhubung ke Jaringan Internet Melalui Terminal"
description = "Lorem ipsum dolor sit amet."
date = 2024-02-02
draft=true
[taxonomies]
tags = ["Linux", "network"]
[extra]
toc = true
+++

## Terhubung ke wifi dengan nmcli

### Persyaratan
untuk mengikuti panduan ini diperlukan untuk menginstall nmcli, tapi biasanya nmcli sudah terinstall disetiap distro linux yang ada, jika `nmcli` belum terinstall, maka nmcli bisa diinstall dengan menjalankan perintah berikut di terminal:
#### Debian dan turunannya
```bash
sudo apt install nmcli
```
#### Fedora
```bash
sudo dnf install NetworkManager
```

### Step 1: scan koneksi yang tersedia
Pindai koneksi wifi yang tersedia disekitar device, untuk melakukannya gunakan perintah ini:
```bash
  nmcli dev wifi list 
```
{{ image(url="1.png", alt="This is an image" no_hover=true) }}

### Step 2: hubungkan ke wifi
```sh
  nmcli --ask dev wifi connect <SSID>
```
{{ image(url="2.png", alt="This is an image" no_hover=true) }}

### Step 3: verifikasi koneksi wifi
Tahapan ini dilakukan untuk memverifikasi bahwa wi-fi yang tersambung sudah bisa terhubung ke internet, untuk memverikasinya bisa dengan mengakses situs web di browser atau melakukan ping ke jaringan melalui terminal
```sh
ping google.com
```
{{ image(url="3.png", alt="This is an image" no_hover=true) }}

## Menghubungkan kembali ke device yang sudah pernah terkoneksi
Jika terputus dari koneksi yang disimpan sebelumnya, kamu dapat terhubung kembali ke jaringan itu dengan mengikuti langkah-langkah berikut
-  Lihat daftar koleksi yang pernah tersambung
```sh
  nmcli con show
```
{{ image(url="4.png", alt="This is an image" no_hover=true) }}

- Hubungkan kembali ke perangkat yang ada
```sh
  nmcli con up <SSID>
```
{{ image(url="5.png", alt="This is an image" no_hover=true) }}

## Bacaan Lebih Lanjut
<a class="external" href="https://developer-old.gnome.org/NetworkManager/stable/nmcli.html">dokumentasi nmcli</a>