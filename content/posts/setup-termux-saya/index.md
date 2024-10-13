---
title: "Setup Termux Saya"
Slug: "setup-termux-saya"
date: 2024-10-10
categories:
  - Termux
tags:
  - Termux
  - Setup
DescriptionSEO: "Cara setup termux untuk pemula"
description: ""
comments: false
draft: false
---

Bagi saya termux adalah salah satu aplikasi favorit yang sangat sering saya gunakan, mulai dari untuk mengatur performa hp, mengelola repositori di github, sampai ngeblog pun juga saya lakukan di aplikasi ini.

Nah! Agar termux bisa digunakan untuk menghandle kegiatan saya, maka ada beberapa hal yang perlu saya lakukan. 

Kamu juga bisa mencoba setup ini jika kamu bingung dengan apa yang harus di lakukan saat setelah menginstal termux.

## Persiapan

- Mengubah Lokasi Mirror

```shell
termux-change-repo
```

Di sini saya memilih **Single Mirror** - **DomaiNesia**

- Izinkan Akses penyimpanan

```shell
termux-setup-storage
```

- Perbarui Package

```shell
pkg update && pkg upgrade
```

---

## Menghubungkan Ke Github

- Instal Git

```shell
pkg install git
```

- Membuat Folder SSH

```shell
mkdir .ssh
```

- Pindah Ke Folder SSH

```shell
cd .ssh
```

- Generate **Public Key** dan **Private Key**

```shell
ssh-keygen -t ed25519 -C "emailkamu@gmail.com"
```

Akan muncul permintaan untuk mengisikan sesuatu, disini akan saya skip saja dengan menekan `Enter`

- Salin Isi Public Key

```shell
cat id_ed25519.pub
```

- Tempel Isi Public Key

https://github.com/settings/keys

- Jalankan SSH Agent

```shell
eval "$(ssh-agent -s)"
```

- Menambahkan Identitas

```shell
ssh-add id_ed25519
```

- Tes Konek Ke Github

```shell
ssh -T git@github.com
```

Di sini akan muncul pilihan **yes/no**, maka izinkan saja dengan mengetikan **yes** lalu tekan `Enter`

---

## Mengganti Shell Bawaan Jadi ZSH

- Instal ZSH

```shell
pkg install zsh
```

- Jadikan ZSH Sebagai Shell Bawaan

```shell
chsh -s zsh
```

- Restart Termux

Tekan `CTRL + D` dan buka kembali aplikasi termux

---

## Kustomisasi ZSH

Saya ingin mengganti tulisan Welcome Termux menjadi neofetch.

- Instal Neofetch

```shell
pkg install neofetch
```

- Menghapus Tulisan Welcome Termux

```shell
rm ../usr/etc/motd
```

- Instal Curl

```shell
pkg install curl
```

- Instal oh-my-zsh

```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

- Instal Plugin Auto Suggestions

```shell
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

- Instal Plugin Syntax Highlighting

```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

- Edit File zshrc

```shell
nano ~/.zshrc
```

- Cari tulisan

```shell
plugins=(git)
```

- Ganti jadi seperti ini

```shell
plugins=(
git
zsh-autosuggestions
zsh-syntax-highlighting
)
```

- Keluar dan Save 

	- Tekan tombol `CTRL + X` 
	- lalu `y` 
	- dan `Enter`

Referensi:

