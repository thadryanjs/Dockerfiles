FROM fedora:latest
RUN dnf install -y wget git make clang python3-pip neovim tmux nodejs \ 
    && wget https://repo.anaconda.com/archive/Anaconda3-2023.07-1-Linux-x86_64.sh \
    && yes | sh Anaconda3-2023.07-1-Linux-x86_64.sh -b \
    && echo "export PATH=/root/anaconda3/bin:$PATH" >> ~/.bashrc \
    && dnf install -y R \
    && wget https://github.com/quarto-dev/quarto-cli/releases/download/v1.3.361/quarto-1.3.361-linux-amd64.tar.gz \
    && sudo tar -C /opt -xvzf quarto-1.3.361-linux-amd64.tar.gz \
    && ln -s /opt/quarto-1.3.361/bin/quarto /bin/quarto \
    && git clone https://github.com/thadryanjs/nvim.git ~/.config
