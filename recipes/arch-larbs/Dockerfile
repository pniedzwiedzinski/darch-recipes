FROM pniedzwiedzinski/arch-common

RUN pacman -S --noconfirm --needed \
      xorg \
      nettle \
      zsh \
      xterm \
      dbus \
      noto-fonts-extra \
      ttf-liberation \
      xcompmgr \
    && yay_as_root brave-bin \
    && yay_as_root ranger \
    && yay_as_root python-ueberzug

COPY script /tmp/script

RUN /tmp/script

# Make dotfiles default global configuration
RUN mkdir -p /etc/dunst \
    && cp /home/guest/.config/i3/config /etc/i3/config \
    && cp /home/guest/.config/i3blocks/config /etc/i3block.conf \
    && cp /home/guest/.config/dunst/dunstrc /etc/dunst/dunstrc \
    && cp /home/guest/.config/fontconfig/fonts.conf /etc/fonts/local.conf \
    && cp -r /home/guest/.config/vifm /etc/vifm \
    && cp -r /home/guest/.config/mpv /etc/mpv \
    && cp /home/guest/.config/nvim/init.vim /etc/xdg/nvim/sysinit.vim \
    && cp /home/guest/.config/zathura/zathurarc /etc/zathurarc \
    && cp /home/guest/.xinitrc /etc/X11/xinit/xinitrc \
    && sed s/^# ssh-agent i3/ssh-agent i3/ /etc/X11/xinit/xinitrc \
    && sed s/^ssh-agent dwm/#ssh-agent dwm/ /etc/X11/xinit/xinitrc \
    && cp -r /home/guest/.local/bin /usr/local/larbs \
    && sed 's/dunst &/dunst -conf \/etc\/dunst\/dunstrc/' /home/guest/.xprofile \
    && echo "export PATH=$PATH:/usr/local/larbs:/usr/local/larbs/statusbar:/usr/local/larbs/i3cmds:/usr/local/larbs/cron" >> /etc/profile

# Install utils
RUN pacman -S --noconfirm \
      pavucontrol \
      gtk2 \
    && yay_as_root j4-dmenu-desktop
