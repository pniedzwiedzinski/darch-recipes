FROM pniedzwiedzinski/arch-ltd

COPY mkinitcpio.conf /etc/mkinitcpio.conf

RUN sudo -u '#1000' yay -S --noconfirm \
	plymouth
