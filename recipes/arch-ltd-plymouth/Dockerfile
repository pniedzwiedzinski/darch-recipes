FROM pniedzwiedzinski/arch-ltd

COPY mkinitcpio.conf /etc/mkinitcpio.conf
COPY grub /etc/default/grub

RUN sudo -u '#1000' yay -S --noconfirm \
	plymouth \
    && cat /etc/plymouth/plymouthd.conf
