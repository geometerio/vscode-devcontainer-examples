FROM elixir:1.11.1

RUN apt-get update \
    && apt-get install -y zsh

RUN sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

CMD ["iex", "-S", "mix"]

