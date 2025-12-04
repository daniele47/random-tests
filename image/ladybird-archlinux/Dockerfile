FROM archlinux

ARG CLEAN_VCPKG=true

RUN groupadd -r lb && \
    useradd -r -g lb -m -d /app lb && \
    mkdir -p /app && chown lb:lb /app

RUN pacman -S --noconfirm --needed autoconf-archive automake base-devel ccache cmake curl libgl nasm ninja qt6-base qt6-tools qt6-wayland ttf-liberation tar unzip zip libpulse git && pacman -Scc --noconfirm

USER lb

RUN git clone https://github.com/LadybirdBrowser/ladybird /app/ladybird && \
    cd /app/ladybird && ./Meta/ladybird.py build && ! ./Meta/ladybird run && \
    if [ "$CLEAN_VCPKG" = "true" ]; then \
        mkdir /app/lb/; \
        mv /app/ladybird/Build/release/{bin,lib64,libexec,share} /app/lb/; \
        rm -rf /app/ladybird; \
        mv /app/lb /app/ladybird; \
    fi

USER root

RUN chown -R root:root /app && chmod 777 /app

