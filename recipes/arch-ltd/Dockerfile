FROM pniedzwiedzinski/arch-larbs-thinkpad

RUN pacman -S --noconfirm \
      docker \
      emacs \
    && sudo -u #1000 yay -S --noconfirm \
      github-cli \
      qrcp \
      alacritty \
      docker-compose \
      ripgrep
