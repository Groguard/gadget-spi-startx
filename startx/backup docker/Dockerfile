FROM arm32v7/debian:stretch-slim

RUN apt-get -yqq update && apt-get install --no-install-recommends -y \
       xserver-xorg-video-fbdev xinit xterm lxdm openbox libgl1-mesa-dri \
       xserver-xorg-input-evdev

RUN apt-get -y clean && rm -rf /var/lib/apt/lists/*
       
RUN rm /usr/lib/arm-linux-gnueabihf/dri/vc4_dri.so \
    /usr/lib/arm-linux-gnueabihf/dri/virtio_gpu_dri.so \
    /usr/lib/arm-linux-gnueabihf/dri/vmwgfx_dri.so \
    /usr/lib/arm-linux-gnueabihf/dri/msm_dri.so \
    /usr/lib/arm-linux-gnueabihf/dri/nouveau_dri.so \
    /usr/lib/arm-linux-gnueabihf/dri/nouveau_vieux_dri.so \
    /usr/lib/arm-linux-gnueabihf/dri/r200_dri.so \
    /usr/lib/arm-linux-gnueabihf/dri/r300_dri.so \
    /usr/lib/arm-linux-gnueabihf/dri/r600_dri.so \
    /usr/lib/arm-linux-gnueabihf/dri/radeon_dri.so \
    /usr/lib/arm-linux-gnueabihf/dri/radeonsi_dri.so

RUN touch /root/.Xauthority

RUN sed -i 's|# autologin=dgod|autologin=root|g' /etc/lxdm/default.conf

CMD ["startx"]
