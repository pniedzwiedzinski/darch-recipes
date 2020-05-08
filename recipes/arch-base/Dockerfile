FROM godarch/arch:latest

COPY mkinitcpio.conf /etc/mkinitcpio.conf
COPY mirrorlist /etc/pacman.d/mirrorlist

RUN pacman -S --noconfirm \
      linux \
      linux-firmware \
      networkmanager \
      base-devel \
    && systemctl enable NetworkManager

# Path makepkg so it can be run as root
RUN curl https://gist.githubusercontent.com/pauldotknopf/ff8e986225ab2f264acea1a5bb0c6c5a/raw/5c26a163f7815682793001312b0bd693bebb3d45/makepkg.patch | patch /usr/bin/makepkg

