FROM pniedzwiedzinski/arch-larbs-thinkpad

RUN pacman -S --noconfirm \
      docker \
      emacs \
    && echo "guest ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers \
    && sudo -u '#1000' yay -S --noconfirm \
      github-cli \
      qrcp \
      alacritty \
      docker-compose \
      ripgrep \
    && sed '/^guest ALL=(ALL) NOPASS/d' /etc/sudoers
