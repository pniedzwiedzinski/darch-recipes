FROM godarch/arch:latest

COPY mkinitcpio.conf /etc/mkinitcpio.conf

RUN pacman -S --noconfirm \
      linux \
      linux-firmware \
      networkmanager \
      base-devel \
    && systemctl enable NetworkManager



