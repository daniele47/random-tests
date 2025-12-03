FROM fedora

RUN groupadd -r lb && \
    useradd -r -g lb -M lb

ENV HOME=/tmp

RUN dnf install autoconf-archive automake ccache cmake curl git libdrm-devel liberation-sans-fonts libglvnd-devel libtool nasm ninja-build patchelf perl-FindBin perl-IPC-Cmd perl-lib perl-Time-Piece qt6-qtbase-devel qt6-qttools-devel qt6-qtwayland-devel tar unzip zip zlib-ng-compat-static -y && dnf clean all -y

RUN mkdir -p /opt/build && chown lb:lb /opt/build

USER lb

RUN git clone https://github.com/LadybirdBrowser/ladybird /opt/build/ladybird

RUN cd /opt/build/ladybird && ./Meta/ladybird.py build

ENV HOME=
