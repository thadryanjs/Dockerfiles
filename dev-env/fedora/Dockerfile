FROM fedora:latest
RUN dnf install -y wget git make clang neovim tmux nodejs julia \
    && wget https://github.com/artempyanykh/marksman/releases/download/2023-07-25/marksman-linux-x64 \
    && mv marksman-linux-x64 marksman \
    && chmod +x marksman \
    && mkdir -p /root/.local/bin \
    && mv marksman /root/.local/bin/ \
    && wget https://repo.anaconda.com/archive/Anaconda3-2023.07-1-Linux-x86_64.sh \
    && yes | sh Anaconda3-2023.07-1-Linux-x86_64.sh -b \
    && echo "export PATH=/root/anaconda3/bin:$PATH" >> ~/.bashrc \
    && /root/anaconda3/bin/conda config --add channels conda-forge \
    && /root/anaconda3/bin/conda config --set auto_activate_base false \
    && /root/anaconda3/bin/conda init bash \
    && julia -e 'using Pkg; Pkg.add("LanguageServer")' \
    && wget https://github.com/quarto-dev/quarto-cli/releases/download/v1.3.361/quarto-1.3.361-linux-amd64.tar.gz \
    && sudo tar -C /opt -xvzf quarto-1.3.361-linux-amd64.tar.gz \
    && ln -s /opt/quarto-1.3.361/bin/quarto /bin/quarto \
    && mkdir -p ~/.config/nvim \
    && git clone https://github.com/thadryanjs/nvim.git ~/.config/nvim \
    && cd ~/.config/nvim \
    && git checkout dev \
    && mkdir -p ~/.config/tmux \
    && git clone https://github.com/thadryanjs/tmux-conf.git ~/.config/tmux \
    && mkdir -p ~/.tmux/plugins/tpm \
    && git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm

# After install:
#    Switch to master branch of nvim
#    Open nvim
#    auth github copilot
#    change back to dev branch of nvim (auth code doesn't show up with fineline)
#    Open tmux and run tpm install
#    run `conda init bash`
