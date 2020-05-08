FROM godarch/arch:latest

COPY mkinitcpio.conf /etc/mkinitcpio.conf
COPY mirrorlist /etc/pacman.d/mirrorlist

RUN pacman -S --noconfirm \
      linux \
      linux-firmware \
      networkmanager \
      systemd \
      base-devel \
    && systemctl enable NetworkManager

RUN ln -s /usr/bin/init /lib/systemd/systemd
