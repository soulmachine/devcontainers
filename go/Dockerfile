FROM mcr.microsoft.com/vscode/devcontainers/go:1.18-bullseye

# References:
#
# * https://github.com/microsoft/vscode-remote-try-go

# switch from root to vscode
USER vscode

RUN sudo apt -qy update && sudo apt -qy --no-install-recommends install \
    build-essential \
    iputils-ping \
 && GO_VERSION=$(curl -s https://go.dev/VERSION?m=text) \
 && curl -O https://dl.google.com/go/$GO_VERSION.linux-amd64.tar.gz \
 && tar -C /usr/local -xzf $GO_VERSION.linux-amd64.tar.gz \
 && rm $GO_VERSION.linux-amd64.tar.gz \
 && sudo apt -qy autoremove && sudo apt clean && sudo rm -rf /var/lib/apt/lists/* && sudo rm -rf /tmp/*
