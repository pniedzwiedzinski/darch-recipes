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
