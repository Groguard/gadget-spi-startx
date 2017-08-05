FROM armhf/alpine

RUN apk update && apk add xf86-video-fbdev xinit xterm lxdm openbox \
        mesa-dri-swrast xorg-server xf86-input-evdev dbus

COPY xorg.conf /etc/X11/xorg.conf

RUN touch /root/.Xauthority

RUN sed -i 's|# autologin=dgod|autologin=root|g' /etc/lxdm/lxdm.conf
RUN sed -i 's/startxfce4/openbox-session/' /etc/X11/xinit/xinitrc

ADD startx.sh /

CMD ["/bin/sh", "/startx.sh"]
