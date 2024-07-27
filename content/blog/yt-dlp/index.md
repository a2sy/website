+++
authors = ["Arif"]
title = "Cara mudah download video menggunakan yt-dlp"
description = "Download video dengan mudah dari YouTube, bilibili, dan berbagai platform streaming video lainnya dengan yt-dlp."
date = 2024-07-27
draft=false
[taxonomies]
tags = ["cli"]
[extra]
toc = true
+++

Mendownload video dari internet kini menjadi lebih mudah, apalagi dengan adanya tools yang dapat dengan mudah membantu kita melakukannya. Misalnya dengan bantuan situs web yang banyak beredar di internet. Video yang diunduh dari situs-situs web itu mungkin saja disisipi didalamnya malware berbahaya, atau terpaksa diarahkan untuk menonton iklan yang mengganggu sebelum bisa mengunduh video. belum lagi kualitas video yang didownload seringkali tidak bagus.<br> Kabar baiknya, `yt-dlp` hadir sebagai solusi yang lebih aman, mudah digunakan, dan juga bersifat open source.

### Apa itu yt-dlp?
[yt-dlp](https://github.com/yt-dlp/yt-dlp/) adalah sebuah fork dari [youtube-dl](https://github.com/ytdl-org/youtube-dl). program command-line yang bisa digunakan untuk mengunduh video dan audio dari lebih ratusan website, seperti youtube, bilibili dan [banyak lagi web lainnya](https://github.com/yt-dlp/yt-dlp/blob/master/supportedsites.md). 

dan... gimana cara menggunakannya?
## Langkah-langkah Menggunakan yt-dlp
### Install yt-dlp
Kamu dapat menginstal yt-dlp menggunakan official [realease binary](https://github.com/yt-dlp/yt-dlp/wiki/Installation#using-the-release-binary) ,[pip](https://github.com/yt-dlp/yt-dlp/wiki/Installation#with-pip), atau dengan [package manager](https://github.com/yt-dlp/yt-dlp/wiki/Installation#third-party-package-managers) favoritmu.
##### RELEASE FILES
|File|Description|
|:---|:----------|
|[yt-dlp.exe](https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp.exe)|Windows (Win7 SP1+) standalone x64 binary (recommended for **Windows**)|
|[yt-dlp_macos](https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp_macos)|Universal MacOS (10.15+) standalone executable (recommended for **MacOS**)|
|[yt-dlp](https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp)|Platform-independent zipimport binary. Needs Python (recommended for Linux/BSD)|


Selain itu kamu juga bisa menginstallnya di [android](https://github.com/yt-dlp/yt-dlp/wiki/Installation#android), atau jika kamu kurang familiar dengan command line, tersedia banyak [GUI Apps](https://www.reddit.com/r/youtubedl/wiki/info-guis/) yang bisa digunakan.

### Download video dengan yt-dlp
okee ayok kita mulai, untuk mendownload video bisa dengan memasukkan perintah berikut ke terminal

``` js
yt-dlp 'URL_VIDEO'
```

ganti `URL_VIDEO` dengan url video yang mau kamu download. Misal :
```sh
yt-dlp https://www.youtube.com/watch?v=dQw4w9WgXcQ
```

{{ image(url="1.png", alt="This is an image" no_hover=true) }}

masukkan perintah diatas, tekan enter, tunggu proses selesai.. dan selamat video sudah tersedia untuk ditonton

{{ image(url="2.jpg", alt="This is an image" no_hover=true) }}

- Memilih format Video

yt-dlp memungkinkanmu untuk memilih format video yang ingin didownload. Gunakan perintah berikut untuk melihat format yang tersedia:
```sh
yt-dlp -F 'URL_VIDEO'
```
misal:
```sh
yt-dlp -F https://www.youtube.com/watch?v=dQw4w9WgXcQ
```

{{ image(url="3.png", alt="This is an image" no_hover=true) }}
Setelah melihat daftar format, kamu bisa memilih format yang diinginkan dengan menambahkan opsi `-f` diikuti oleh ID.
```sh
yt-dlp -f ID_AUDIO+ID_VIDEO URL_VIDEO
```
misal :
```sh
yt-dlp -f 140+136 https://www.youtube.com/watch?v=dQw4w9WgXcQ
```

{{ image(url="4.jpg", alt="This is an image" no_hover=true) }}
dengan begitu kamu bisa mendapatkan video sesuai dengan kualitas yang kamu mau,dan juga kamu dapat lebih menghemat ruang disk yang kamu punya.

- download dengan kualitas terbaik

Selain memilih format secara manual kamu juga bisa untuk mendownload video dengan kualitas terbaik menggunakan yt-dlp, caranya bisa dengan menggunakan perintah berikut:
```sh
yt-dlp -f bestvideo+bestaudio/best URL_VIDEO
```

misal
```sh
yt-dlp -f bestvideo+bestaudio/best https://www.youtube.com/watch?v=dQw4w9WgXcQ
```

- Download audio saja

jika hanya ingin mendownload audio saja, misalnya dalam format MP3:
```sh
yt-dlp -x --audio-format mp3 https://www.youtube.com/watch?v=dQw4w9WgXcQ
```

- Download seluruh video di playlist
```sh
yt-dlp URL_PLAYLIST
```

- menyimpan video di folder tertentu

tambahkan opsi `-o` untuk menyimpan video ke dalam folder tertentu
```sh
yt-dlp -f bestvideo+bestaudio/best -o "~/Downloads/Playlist/%(playlist)s/%(title)s.%(ext)s" URL_PLAYLIST
```

- lihat opsi lebih lanjut

tambahkan opsi `--help` untuk melihat opsi apa saja yang bisa digunakan
```sh
yt-dlp --help
```

atau bisa juga dilihat [disini](https://github.com/yt-dlp/yt-dlp?tab=readme-ov-file#usage-and-options) 

## Referensi dan bacaan menarik
- [Github repository yt-dlp](https://github.com/yt-dlp/yt-dlp) dan [wiki](https://github.com/yt-dlp/yt-dlp/wiki)
- [Supported sites](https://github.com/yt-dlp/yt-dlp/blob/master/supportedsites.md)
- [Github repository youtube-dl](https://github.com/ytdl-org/youtube-dl)
- [yt-dlp - ArchWiki](https://wiki.archlinux.org/title/Yt-dlp)
- [GUI's for yt-dlp/youtube-dl - r/youtubedl](https://www.reddit.com/r/youtubedl/wiki/info-guis)