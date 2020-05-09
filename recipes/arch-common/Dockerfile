FROM pniedzwiedzinski/arch-base

RUN pacman -S --noconfirm \
      wget \
      git \
      vim \
      ntp

RUN groupadd guest -g 1000 \
    && useradd guest -g 1000 -u 1000 \
    && mkdir -m 744 /home/guest \
    && chown 1000:1000 /home/guest

RUN git clone https://aur.archlinux.org/yay-bin.git /tmp/yay \
    && cd /tmp/yay \
    && chmod 777 /tmp/yay \
    && sudo -u guest makepkg -s --noconfirm \
    && pacman -U --noconfirm --needed /tmp/yay/$(ls /tmp/yay/ | grep tar.xz)

COPY yay_as_root /usr/bin/yay_as_root
