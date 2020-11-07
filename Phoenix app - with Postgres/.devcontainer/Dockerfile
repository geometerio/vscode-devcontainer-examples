ARG DEV_ELIXIR_DOCKER_IMAGE
FROM $DEV_ELIXIR_DOCKER_IMAGE

RUN apt-get update \
    && apt-get install -y apt-utils

# Phoenix requirements:
ARG PHOENIX_VERSION
ARG NODE_MAJOR_VERSION
RUN mix local.hex --force && \
    mix archive.install --force hex phx_new $PHOENIX_VERSION && \
    curl -sL https://deb.nodesource.com/setup_$NODE_MAJOR_VERSION.x | bash && \
    apt-get install -y nodejs build-essential inotify-tools && \
    mix local.rebar --force

ARG HEX_PRIVATE_ORG=""
ARG HEX_PRIVATE_ORG_READ_ONLY_KEY=""
RUN set -eux; \
  if [ ! -z "${HEX_PRIVATE_ORG}" ] && [ ! -z "${HEX_PRIVATE_ORG_READ_ONLY_KEY}" ]; then \
    mix hex.organization auth ${HEX_PRIVATE_ORG} --key ${HEX_PRIVATE_ORG_READ_ONLY_KEY}; \
  fi

# Other developer tools
RUN apt-get install -y neovim

# zsh and Oh My ZSH
RUN apt-get install -y zsh \
    && sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Move aliases to a separate file?
RUN echo "alias s='iex -S mix phx.server'" >> /root/.zshrc
