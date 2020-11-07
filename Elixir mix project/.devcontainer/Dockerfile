ARG DEV_ELIXIR_DOCKER_IMAGE
FROM $DEV_ELIXIR_DOCKER_IMAGE

RUN apt-get update && \
    apt-get install -y apt-utils

RUN mix local.hex --force

ARG HEX_PRIVATE_ORG=""
ARG HEX_PRIVATE_ORG_READ_ONLY_KEY=""
RUN set -eux; \
  if [ ! -z "${HEX_PRIVATE_ORG}" ] && [ ! -z "${HEX_PRIVATE_ORG_READ_ONLY_KEY}" ]; then \
    mix hex.organization auth ${HEX_PRIVATE_ORG} --key ${HEX_PRIVATE_ORG_READ_ONLY_KEY}; \
  fi

# zsh and Oh My Zsh
RUN apt-get install -y zsh && \
  sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Other developer tools
RUN apt-get install -y neovim

