FROM mcr.microsoft.com/vscode/devcontainers/go:1.18-bullseye

# References:
#
# * https://github.com/microsoft/vscode-remote-try-go

# switch from root to vscode
USER vscode

RUN sudo apt -qy update && sudo apt -qy --no-install-recommends install \
    build-essential \
    iputils-ping \
 && echo "Install go tools" \
 && go install github.com/ramya-rao-a/go-outline@latest \
 && go install github.com/cweill/gotests/gotests@latest \
 && go install github.com/fatih/gomodifytags@latest \
 && go install github.com/josharian/impl@latest \
 && go install github.com/haya14busa/goplay/cmd/goplay@latest \
 && go install github.com/go-delve/delve/cmd/dlv@latest \
 && go install honnef.co/go/tools/cmd/staticcheck@latest \
 && go install golang.org/x/tools/gopls@latest \
 && go install github.com/uudashr/gopkgs/v2/cmd/gopkgs@latest \
 && go install golang.org/x/lint/golint@latest \
 && go install golang.org/x/tools/cmd/goimports@latest \
 && go install mvdan.cc/gofumpt@latest \
 && sudo apt -qy autoremove && sudo apt clean && sudo rm -rf /var/lib/apt/lists/* && sudo rm -rf /tmp/*
