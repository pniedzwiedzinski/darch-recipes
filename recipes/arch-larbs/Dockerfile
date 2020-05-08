FROM pniedzwiedzinski/arch-common

COPY script /tmp/script

RUN /tmp/script

RUN pacman -S --noconfirm --needed \
      zsh \
      xterm \
      dbus \
      noto-fonts-extra \
      ttf-liberation \
      brave-bin
