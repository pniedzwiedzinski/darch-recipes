FROM godarch/arch:latest

COPY mkinitcpio.conf /etc/mkinitcpio.conf
COPY mirrorlist /etc/pacman.d/mirrorlist

RUN pacman -S --noconfirm \
      linux \
      linux-firmware \
      networkmanager \
      base-devel \
    && systemctl enable NetworkManager

RUN ln -s /lib/systemd/systemd /sbin/init
