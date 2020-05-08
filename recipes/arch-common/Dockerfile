FROM pniedzwiedzinski/arch-base

RUN pacman -S --noconfirm \
      wget \
      git \
      vim \
      ntp

RUN git clone https://aur.archlinux.org/yay-bin.git /tmp/yay \
    && cd /tmp/yay \
    && chmod 777 /tmp/yay \
    && sudo -u guest makepkg -s --noconfirm \
    && pacman -U --noconfirm --needed /tmp/yay/$(ls /tmp/yay/ | grep tar.xz)
