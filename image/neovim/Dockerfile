FROM fedora

RUN dnf -y install ninja-build cmake gcc make gettext curl glibc-gconv-extra git zip && dnf clean all -y

RUN git clone https://github.com/neovim/neovim ~/neovim

RUN cd ~/neovim && make CMAKE_BUILD_TYPE=RelWithDebInfo && make install && make CMAKE_INSTALL_PREFIX=~/nvim-install install && cd ~/ && zip -r nvim.zip nvim-install

WORKDIR /root
