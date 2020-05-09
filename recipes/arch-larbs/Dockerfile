FROM pniedzwiedzinski/arch-common

RUN pacman -S --noconfirm --needed \
      xorg \
      zsh \
      xterm \
      dbus \
      noto-fonts-extra \
      ttf-liberation \
    && yay_as_root brave-bin

COPY script /tmp/script

RUN /tmp/script

RUN mkdir -p /etc/dunst

# Make dotfiles global configuration
RUN cp /home/guest/.config/i3/config /etc/i3/config \
    && cp /home/guest/.config/i3blocks/config /etc/i3block.conf \
    && cp /home/guest/.config/dunst/dunstrc /etc/dunst/dunstrc \
    && cp /home/guest/.config/fontconfig/fonts.conf /etc/fonts/local.conf \
    && cp -r /home/guest/.config/vifm /etc/vifm \
    && cp -r /home/guest/.config/mpv /etc/mpv \
    && cp /home/guest/.config/nvim/init.vim /etc/xdg/nvim/sysinit.vim \
    && cp /home/guest/.config/zathura/zathurarc /etc/zathurarc \
    && sed 's/dunst &/dunst -conf \/etc\/dunst\/dunstrc/' /home/guest/.config/xprofile


