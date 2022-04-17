FROM mcr.microsoft.com/vscode/devcontainers/typescript-node:16-bullseye

# References:
#
# * https://github.com/microsoft/vscode-dev-containers/tree/main/containers/typescript-node
# * https://hardhat.org/getting-started/
# * https://docs.soliditylang.org/en/latest/installing-solidity.html#linux-packages

# switch from root to node
USER node

RUN sudo apt -qy update && sudo apt -qy --no-install-recommends install \
    build-essential \
    iputils-ping \
 && echo "deb http://ppa.launchpad.net/ethereum/ethereum/ubuntu focal main" | sudo tee /etc/apt/sources.list.d/ethereum.list \
 && sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 1C52189C923F6CA9 \
 && sudo apt -qy update \
 && sudo apt -qy install abigen \
 && wget https://github.com/ethereum/solidity/releases/download/v0.8.13/solc-static-linux -O /tmp/solc && chmod +x /tmp/solc && sudo mv /tmp/solc /usr/local/bin/ \
 && npm install -g ts-node hardhat solhint surya prettier prettier-plugin-solidity solhint-plugin-prettier npm-check-updates \
 && sudo apt -qy autoremove && sudo apt clean && sudo rm -rf /var/lib/apt/lists/* && sudo rm -rf /tmp/*
