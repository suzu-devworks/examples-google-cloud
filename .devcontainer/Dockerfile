FROM mcr.microsoft.com/devcontainers/base:bookworm as dev-stage

## Configure apt and install packages
# https://cloud.google.com/sdk/docs/install-sdk?hl=ja
RUN set -x \
    && echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] https://packages.cloud.google.com/apt cloud-sdk main" | tee -a /etc/apt/sources.list.d/google-cloud-sdk.list \
    && curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo gpg --dearmor -o /usr/share/keyrings/cloud.google.gpg \
    && apt update -y \
    && apt install google-cloud-sdk -y
