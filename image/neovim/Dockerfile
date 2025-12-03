FROM fedora

RUN sudo dnf -y install ninja-build cmake gcc make gettext curl glibc-gconv-extra git

RUN git clone https://github.com/neovim/neovim ~/neovim

RUN cd ~/neovim && make CMAKE_BUILD_TYPE=RelWithDebInfo && sudo make install

WORKDIR /root/neovim
