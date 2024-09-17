FROM alpine:3.20.3

WORKDIR /home/seanime

ENV HOME=/home/seanime \
    PKGVER=2.1.1

RUN apk update && apk add --no-cache \
    qbittorrent-nox \
    bash \
    mpv \
    vim \
    ffmpeg \
    wget \
    tar \
    curl \
    libstdc++ \
    boost-system \
    boost-program_options \
    qt5-qtbase \
    libtorrent-rasterbar 

RUN wget -q https://github.com/5rahim/seanime/releases/download/v${PKGVER}/seanime-${PKGVER}_Linux_x86_64.tar.gz \
    && tar -xvzf seanime-${PKGVER}_Linux_x86_64.tar.gz \
    && rm seanime-${PKGVER}_Linux_x86_64.tar.gz  

EXPOSE 43211 8080

CMD ["sh", "-c", "qbittorrent-nox --daemon & exec ./seanime"]
