# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.166.1/containers/java/.devcontainer/base.Dockerfile

# [Choice] Java version: 11, 15
ARG VARIANT="15"
FROM mcr.microsoft.com/vscode/devcontainers/java:0-${VARIANT}

# Install additional OS packages
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
    wixl \
    python3-pip

# Install Maven
ARG MAVEN_VERSION=""
RUN su vscode -c "umask 0002 && . /usr/local/sdkman/bin/sdkman-init.sh && sdk install maven \"${MAVEN_VERSION}\""

# Install Node.js
ARG NODE_VERSION="lts/*"
RUN su vscode -c "umask 0002 && . /usr/local/share/nvm/nvm.sh && nvm install ${NODE_VERSION} 2>&1"

# Install global node packages
RUN su vscode -c "source /usr/local/share/nvm/nvm.sh && npm install -g \
    markdownlint-cli \
    " 2>&1

# Install Python packages
RUN pip3 install \
    pre-commit==2.12.1 \
    detect-secrets==1.1.0 \
    setuptools==39.1.0

# Install launch4j
RUN curl -SOLJ https://sourceforge.net/projects/launch4j/files/launch4j-3/3.14/launch4j-3.14-linux-x64.tgz/download && \
    tar zxvf launch4j-3.14-linux-x64.tgz -C /usr/bin && \
    rm launch4j-3.14-linux-x64.tgz
