FROM alpine:3.20.3

WORKDIR /home/seanime

# Set environment variables
ENV HOME=/home/seanime
ENV PKGVER=2.1.1

# Install qBittorrent-nox and necessary dependencies
RUN apk add --no-cache qbittorrent-nox bash mpv  vim ffmpeg wget tar curl libstdc++ boost-system boost-program_options qt5-qtbase libtorrent-rasterbar

# Download and extract Seanime
RUN wget https://github.com/5rahim/seanime/releases/download/v${PKGVER}/seanime-${PKGVER}_Linux_x86_64.tar.gz \
    && tar -xvzf seanime-${PKGVER}_Linux_x86_64.tar.gz

# Expose the necessary ports for Seanime and qBittorrent
EXPOSE 43211 8080

# Start qBittorrent-nox daemon in the background and then Seanime
CMD ["sh", "-c", "qbittorrent-nox --daemon & ./seanime"]
