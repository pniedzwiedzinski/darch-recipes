FROM godarch/arch:latest

COPY mkinitcpio.conf /etc/mkinitcpio.conf
COPY mirrorlist /etc/pacman.d/mirrorlist

RUN pacman -S --noconfirm \
      linux \
      linux-firmware \
      networkmanager \
      systemd \
      systemd-sysvcompat \
      base-devel \
    && systemctl enable NetworkManager

RUN ln -s /lib/systemd/systemd /usr/bin/init
