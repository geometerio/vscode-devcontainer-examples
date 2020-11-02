FROM elixir:1.11.1

RUN apt-get update \
    && apt-get install -y apt-utils

# zsh and Oh My ZSH
RUN apt-get install -y zsh \
    && sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Phoenix requirements:
RUN mix local.hex --force \
    && mix archive.install --force hex phx_new 1.5.6 \
    && curl -sL https://deb.nodesource.com/setup_14.x | bash \
    && apt-get install -y nodejs \
    && apt-get install -y build-essential \
    && apt-get install -y inotify-tools \
    && mix local.rebar --force

# Other developer tools
RUN apt-get install -y neovim

# Move aliases to a separate file?
RUN echo "alias s='iex -S mix phx.server'" >> /root/.zshrc

CMD ["iex", "-S", "mix", "phx.server"]
