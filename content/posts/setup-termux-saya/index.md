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

## Persiapan

- Pindah Lokasi Mirror

```shell
termux-change-repo
```

- Izinkan Akses penyimpanan

```shell
termux-setup-storage
```

- Update dan Upgrade Package

```shell
pkg update && pkg upgrade
```

---

## Menghubungkan Ke Github

- Install Git

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

- Membuat **Public Key** dan **Private Key**

```shell
ssh-keygen -t ed25519 -C "emailkamu@gmail.com"
```

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

- Konek Ke Github

```shell
ssh -T git@github.com
```

Jika di suruh memasukkan sesuatu ketikan saja **yes** lalu **Enter**

---

## Mengganti Shell Bawaan Jadi ZSH

- Instal ZSH

```shell
pkg install zsh
```

- Mendikan ZSH Sebagai Shell Bawaan

```shell
chsh -s zsh
```
---

## Kustomisasi ZSH

- Instal Git dan Curl

```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

- Install Plugin Auto Suggestions

```shell
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

- Install Plugin Syntax Highlighting

```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

- Mengakifkan Plugin

```shell
nano ~/.zshrc
```

Cari tulisan

```shell
plugins=(git)
```

Lalu ganti jadi seperti ini

```shell
plugins=(
git
zsh-autosuggestions
zsh-syntax-highlighting
)
```