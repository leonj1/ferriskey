FROM mcr.microsoft.com/devcontainers/rust:1-bookworm

USER root
RUN apt-get update \
    && apt-get install -y --no-install-recommends pkg-config libssl-dev xmlsec1 \
    && rm -rf /var/lib/apt/lists/*

USER vscode
RUN rustup update stable \
    && rustup default stable \
    && rustup component add rustfmt clippy \
    && cargo install sqlx-cli --version 0.8.6 --locked --no-default-features --features postgres
