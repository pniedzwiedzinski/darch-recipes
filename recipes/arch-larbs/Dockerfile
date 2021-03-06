FROM pniedzwiedzinski/arch-common

RUN git clone https://aur.archlinux.org/libxft-bgra.git /tmp/libxft-bgra \
    && cd /tmp/libxft-bgra \
    && chmod 777 /tmp/libxft-bgra \
    && sudo -u '#1000' makepkg -s --noconfirm --skippgpcheck \
    && pacman -U *.pkg.tar.xz --noconfirm


RUN pacman -S --noconfirm --needed \
      xorg \
      nettle \
      zsh \
      xterm \
      dbus \
      noto-fonts-extra \
      ttf-liberation \
      xcompmgr \
      htop \
      sxhkd \
    && sudo -u '#1000' yay -S --noconfirm --needed \
      brave-bin \
      ranger \
      python-ueberzug


COPY script /tmp/script

RUN /tmp/script

# Make dotfiles default global configuration
RUN mkdir -p /etc/dunst \
    && cp /home/guest/.config/dunst/dunstrc /usr/share/dunst/dunstrc \
    && cp /home/guest/.config/fontconfig/fonts.conf /etc/fonts/local.conf \
    && cp -r /home/guest/.config/vifm /etc/vifm \
    && cp -r /home/guest/.config/mpv /etc/mpv \
    && cp /home/guest/.config/nvim/init.vim /etc/xdg/nvim/sysinit.vim \
    && cp /home/guest/.config/zathura/zathurarc /etc/zathurarc \
    && cp /home/guest/.xinitrc /etc/X11/xinit/xinitrc \
    && cp -r /home/guest/.local/bin /usr/local/larbs \
    && echo "export PATH=$PATH:/usr/local/larbs:/usr/local/larbs/statusbar:/usr/local/larbs/i3cmds:/usr/local/larbs/cron" >> /etc/profile

# Install utils
RUN pacman -S --noconfirm --needed \
      pavucontrol \
      gtk2
