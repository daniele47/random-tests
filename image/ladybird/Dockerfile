FROM fedora

ARG CLEAN_VCPKG=true

RUN groupadd -r lb && \
    useradd -r -g lb -m -d /app lb && \
    mkdir -p /app && chown lb:lb /app

RUN dnf install autoconf-archive automake ccache cmake curl git libdrm-devel liberation-sans-fonts libglvnd-devel libtool nasm ninja-build patchelf perl-FindBin perl-IPC-Cmd perl-lib perl-Time-Piece qt6-qtbase-devel qt6-qttools-devel qt6-qtwayland-devel tar unzip zip zlib-ng-compat-static -y && dnf clean all -y

USER lb

RUN git clone https://github.com/LadybirdBrowser/ladybird /app/ladybird && \
    cd /app/ladybird && ./Meta/ladybird.py build && \
    if [ "$CLEAN_VCPKG" = "true" ]; then \
        rm -rf /app/ladybird/Build/{vcpkg,cache} ; \
    fi

USER root
