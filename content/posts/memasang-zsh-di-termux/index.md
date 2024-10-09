---
title: "Memasang ZSH di Termux"
Slug: "memasang-zsh-di-termux"
date: 2024-09-12
categories:
  - Termux
tags:
  - Termux
  - ZSH
  - Shell
DescriptionSEO: "Cara mudah memasang shell ZSH di termux"
comments: false
draft: false
---

Sebelumnya kita sudah membahas tentang apa yang harus di lakukan saat baru [**pertama kali menginstal termux**](https://dridani.my.id/setup-termux-pemula), nah kali ini kita akan mulai sedikit melakukan kustomisasi dengan mengubah shell bawaan termux yang awalnya **BASH** menjadi **ZSH**

## Apa itu ZSH?

Secara singkat **_Z shell_** atau biasa disebut **ZSH** adalah sebuah alternatif dari jenis varian program bernama **Shell**, fungsi zsh sendiri sama halnya dengan fungsi shell pada umumnya yaitu, tempat kita mengetik untuk memberikan perintah ke dalam komputer.

Ada beberapa contoh varian dari shell seperti **BASH**, **FISH**, **PowerShell** **(bawaan windows)**, dan yang akan kita pasang kali ini yaitu **ZSH**.

## Memasang ZSH

Secara defaut, shell yang terpasang di termux adalah Bash. Disini kita akan memasang dan menjadikan zsh sebagai default shell di termux, caranya ketikkan saja perintah di bawah ini.

### Update & Upgrade Package

```shell
pkg update && pkg upgrade -y
```

### Instal ZSH

```shell
pkg install zsh
```

### Menjadikan ZSH sebagai Shell Bawaan

```shell
chsh -s zsh
```

### Mulai Ulang Termux

Tekan tombol `CTRL + D` atau ketik

```shell
exit
```

## Penutup

Gimana gaes, mudah bukan? dengan ini kamu sudah bisa mengubah zsh sebagai shell default/bawaan di termux kamu. Nah mungkin kamu ingin menambah sentuhan-sentuhan atau kustomisasi seperti tema atau plugin, kalo kamu tertarik yuk lanjut.