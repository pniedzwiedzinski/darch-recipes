# LARBS (not stable)

[LARBS](http://larbs.xyz) deployed on darch

## Usage

```
darch images pull pniedzwiedzinski/arch-larbs
darch stage upload pniedzwiedzinski/arch-larbs
```

There is a preconfigured user `guest` (uid: `1000`, gid: `1000`), that you can log on with password `guest`

## Customization

Changing user

```sh
#!/bin/sh

usermod -l pn -d /home/pn guest
groupmod -n pn guest
groupadd sudo
usermod -aG sudo pn

cp shadow /etc/shadow

ln -sf /usr/share/zoneinfo/Europe/Warsaw /etc/localtime

```
