FROM fedora

RUN groupadd -r appuser && \
    useradd -r -g appuser -m appuser

RUN sudo dnf -y install ninja-build cmake gcc make gettext curl glibc-gconv-extra git

USER appuser

RUN git clone https://github.com/neovim/neovim ~/neovim

RUN cd ~/neovim && make CMAKE_BUILD_TYPE=RelWithDebInfo && sudo make install

WORKDIR ~/neovim
