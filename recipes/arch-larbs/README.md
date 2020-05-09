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

```Dockerfile
FROM pniedzwiedzinski/arch-larbs

RUN usermod -l user -d /home/user guest \
    && echo -e "user:password" | chpasswd

# You probably also want to have access to sudo
RUN usermod -aG sudo user
```
