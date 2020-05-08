FROM pniedzwiedzinski/arch-base

RUN pacman -S --noconfirm \
      curl \
      wget \
      git \
      vim \
      ntp

RUN git clone https://aur.archlinux.org/yay.git /tmp/yay \
    && cd /tmp/yay \
    && makepkg -si
