FROM arm32v7/debian:stretch-slim

RUN apt-get -yqq update && apt-get install --no-install-recommends -y \
       xserver-xorg xserver-xorg-video-fbdev xinit pciutils xinput \
       xfonts-100dpi xfonts-75dpi xfonts-scalable

CMD ["startx"]
