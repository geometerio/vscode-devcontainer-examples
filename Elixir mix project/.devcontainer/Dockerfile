FROM elixir:1.11.1

RUN apt-get update \
    && apt-get install -y apt-utils

# zsh and Oh My Zsh
RUN apt-get install -y zsh
RUN sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Other developer tools
RUN apt-get install -y neovim

CMD ["iex", "-S", "mix"]

