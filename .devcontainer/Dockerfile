# SynLearn DevOps Associate lab image. Debian 12 "bookworm", kept small for the
# 15 GB-month Codespaces storage quota. Docker and Terraform come from features.
FROM mcr.microsoft.com/devcontainers/base:2-bookworm

# ansible-core 2.19 is the newest line that supports bookworm's Python 3.11.
ARG ANSIBLE_CORE_VERSION=2.19.13

RUN apt-get update \
    && apt-get install -y --no-install-recommends python3 python3-venv pipx jq \
    && PIPX_HOME=/opt/pipx PIPX_BIN_DIR=/usr/local/bin \
       pipx install --pip-args=--no-cache-dir "ansible-core==${ANSIBLE_CORE_VERSION}" \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /root/.cache
