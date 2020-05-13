# My darch recipes

These are my os recipes for [Darch](https://github.com/godarch/darch).

## Images

Each image is bootable and ready to go

- [pniedzwiedzinski/arch-base](recipes/arch-base) (user: root, passwd: none)
- [pniedzwiedzinski/arch-common](recipes/arch-common) (user: guest, passwd: guest)
- [pniedzwiedzinski/arch-larbs](recipes/arch-larbs) (user: guest, passwd: guest)

## Usage

```
darch pull pniedzwiedzinski/$image
darch stage upload pniedzwiedzinski/$image
```

## Customization

You probably want to customize your system to your needs :wink:

Here's my customization script:

```sh
#!/bin/sh

## User configuration (name, home, groups, password)
usermod -l pn -d /home/pn guest
groupmod -n pn guest
groupadd sudo
usermod -aG sudo pn

cp shadow /etc/shadow

## Region configuration (timezone, keymap, mirrorlist)
ln -sf /usr/share/zoneinfo/Europe/Warsaw /etc/localtime

cp 00-keyboard.conf /etc/X11/xorg.conf.d/00-keyboard.conf

cp mirrorlist /etc/pacman.d/mirrorlist
pacman -Sy


## Custom software
pacman -S docker --noconfirm

systemctl enable docker
usermod -aG docker pn
```
