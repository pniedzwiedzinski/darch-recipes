FROM pniedzwiedzinski/arch-common

RUN pacman -S --noconfirm --needed \
      zsh \
      xterm \
      dbus \
      noto-fonts-extra \
      ttf-liberation \
      brave-bin

COPY script /tmp/script

RUN /tmp/script


