FROM ubuntu:24.04

# Install dependencies
RUN apt update && \
    apt install -y curl git

# Install chezmoi via official script
RUN sh -c "$(curl -fsLS https://chezmoi.io/get)"

# Create chezmoi source directory
RUN mkdir -p /root/.local/share/chezmoi

# Copu dotfiles as the chezmoi source
COPY ./dotfiles /root/.local/share/chezmoi

# Set chezmoi apply as the entrypoint
ENTRYPOINT ["chezmoi", "apply"]

