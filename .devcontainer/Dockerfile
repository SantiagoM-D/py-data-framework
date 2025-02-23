FROM mcr.microsoft.com/devcontainers/python:3.12

# Set the working directory
WORKDIR /workspaces/py-data-framework

# Update packages and install additional tools
RUN apt-get update && apt-get install -y \
    bash-completion \
    git \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Configure Git to mark the directory as safe
RUN git config --global --add safe.directory /workspaces/py-data-framework

# Add a check before activating the virtual environment in .bashrc
RUN echo 'if [ -d "/workspaces/py-data-framework/.venv" ]; then \
    if [ -z "$VIRTUAL_ENV" ]; then \
    source /workspaces/py-data-framework/.venv/bin/activate; \
    fi; \
    fi' >> /home/vscode/.bashrc

# Set the default user
USER vscode

# Define the entrypoint
CMD [ "bash" ]