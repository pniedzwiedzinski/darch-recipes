FROM godarch/arch:latest

COPY mkinitcpio.conf /etc/mkinitcpio.conf
COPY mirrorlist /etc/pacman.d/mirrorlist

RUN pacman -Syyu \
    && pacman -S --noconfirm \
      linux \
      linux-firmware \
      networkmanager \
      base-devel \
    && systemctl enable NetworkManager

RUN cp /lib/systemd/systemd /sbin/init
