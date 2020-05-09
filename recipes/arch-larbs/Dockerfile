FROM pniedzwiedzinski/arch-common

RUN pacman -S --noconfirm --needed \
      zsh \
      xterm \
      dbus \
      noto-fonts-extra \
      ttf-liberation \
    && sudo -u guest yay -S brave-bin

COPY script /tmp/script

RUN /tmp/script


