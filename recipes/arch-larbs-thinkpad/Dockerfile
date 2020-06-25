FROM pniedzwiedzinski/arch-larbs

RUN pacman -S --noconfirm \
      acpi_call \
      tpacpi-bat \
      tlp \
    && systemctl enable tlp
#    && yay_as_root dockd \
