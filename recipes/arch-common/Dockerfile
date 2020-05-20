FROM pniedzwiedzinski/arch-base

RUN pacman -S --noconfirm \
      dbus \
      wget \
      git \
      vim \
      ntp \
      grub

RUN groupadd guest -g 1000 \
    && groupadd sudo -g 27 \
    && useradd guest -g 1000 -u 1000 -G sudo \
    && echo "%sudo ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers \
    && mkdir -m 744 /home/guest \
    && chown 1000:1000 /home/guest

RUN git clone https://aur.archlinux.org/yay-bin.git /tmp/yay \
    && cd /tmp/yay \
    && chmod 777 /tmp/yay \
    && sudo -u guest makepkg -s --noconfirm \
    && pacman -U --noconfirm --needed /tmp/yay/$(ls /tmp/yay/ | grep tar.xz)

COPY containerd.toml /etc/containerd/config.toml

RUN sudo -u '#1000' yay -S --noconfirm darch && systemctl enable containerd
