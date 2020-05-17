FROM pniedzwiedzinski/arch-larbs-thinkpad

RUN pacman -S --noconfirm \
      docker \
      emacs \
    && yay_as_root github-cli \
    && yay_as_root qrcp \
    && yay_as_root alacritty \
    && yay_as_root docker-compose
