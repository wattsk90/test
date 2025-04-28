# .devcontainer/Dockerfile
FROM mcr.microsoft.com/dotnet/sdk:8.0

# Install necessary dependencies and tools
RUN apt-get update && apt-get install -y \
    curl \
    unzip \
    zip \
    python3 \
    python3-pip \
    python3-venv \
    build-essential \
    && apt-get clean

# Create and activate a virtual environment, install aws-sam-cli, and symlink
RUN python3 -m venv /opt/venv \
    && . /opt/venv/bin/activate \
    && pip install --upgrade pip \
    && pip install aws-sam-cli \
    && ln -s /opt/venv/bin/sam /usr/local/bin/sam

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# [Optional] Uncomment this line to install global node packages.
# RUN su vscode -c "source /usr/local/share/nvm/nvm.sh && npm install -g <your-package-here>" 2>&1