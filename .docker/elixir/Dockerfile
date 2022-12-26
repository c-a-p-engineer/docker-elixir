FROM elixir:1.14.2

RUN mix local.hex --force && \
  mix archive.install hex phx_new 1.6.3 --force && \
  mix local.rebar --force

WORKDIR /app/src
