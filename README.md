# Elixir Docker
Elixir Docker

## Version
* Elixir 1.14.2
* Phenix 1.6.3

## First Boot

### Docker Up
```
cd .docker
docker compose up -d
```

### Enter Docker Container
```
docker-compose run elixir-phenix bash
```

### phenix new Project
```
cd ./src
mix phx.new . --app demo
```

Use DB Mysql
```
mix phx.new . --app demo --database mysql
```

Do not use DB
```
mix phx.new . --app  demo --no-ecto
```

### DB Setting
Change Config Database
```src\config\dev.exs
# Configure your database
config :my_app, MyApp.Repo,
  adapter: Ecto.Adapters.Postgres,
  username: "postgres",
  password: "postgres",
  database: "my_app_dev",
  hostname: "db",
  pool_size: 10
```

### Dependencies Compile
```
mix deps.compile
```

### DB Create 
```
mix ecto.create
```

### DB Migration 
```
mix ecto.migrate
```

### Dependencies Compile & DB Create & DB Migration 
```
mix deps.compile && mix ecto.create && mix ecto.migrate
```

### IP Setting
Docker Host Connect Need IP Change
```src\config\dev.exs
http: [ip: {127, 0, 0, 1}, port: 4000],
```
↓
```src\config\dev.exs
http: [ip: {0, 0, 0, 0}, port: 4000],
```

### Server Up
```
mix phx.server
```

## Docker Setting
Installed Phenix Add `docker-compose.yml` Auto Booting
```yml:docker-compose.yml
command: mix phx.server
```
