FROM fedora

RUN sudo dnf install autoconf-archive automake ccache cmake curl git libdrm-devel liberation-sans-fonts libglvnd-devel libtool nasm ninja-build patchelf perl-FindBin perl-IPC-Cmd perl-lib perl-Time-Piece qt6-qtbase-devel qt6-qttools-devel qt6-qtwayland-devel tar unzip zip zlib-ng-compat-static -y

RUN git clone https://github.com/LadybirdBrowser/ladybird ~/ladybird

RUN ~/ladybird/Meta/ladybird.py run

