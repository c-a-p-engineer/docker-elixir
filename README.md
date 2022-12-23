# Elixir Docker
Elixir Docker

## Version
* Elixir 1.14.2
* Node 16

## First Boot

### Docker Up
```
cd .docker
docker compose up
```

### phenix new Project
```
mix phx.new . --app my_app
```

### DB Setting
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

### Deps Compile
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

### IP Setting

```
http: [ip: {127, 0, 0, 1}, port: 4000],
```
↓
```http: [ip: {0, 0, 0, 0}, port: 4000],
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
