FROM elixir:1.14.2

RUN apt-get update && apt-get install -y \
    inotify-tools\
 && rm -rf /var/lib/apt/lists/*

RUN mix local.hex --force && \
  mix archive.install hex phx_new 1.6.3 --force && \
  mix local.rebar --force

WORKDIR /app/src
