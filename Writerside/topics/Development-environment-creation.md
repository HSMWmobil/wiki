# Development environment creation

This shows different ways for running a development instance

## Content

1. [Docker (docker compose)](#docker-docker-compose)
2. [Docker (dev containers)](#docker-dev-containers)
3. [Python (standalone)](#python-standalone)

## Docker (docker compose)

To run a simple instance for testing your code just start the api as follows.

> This has no live reload. For every change you have to restart and rebuild the container. 
{style="note"}

1. Copy the `example.dev.env` and rename it to `.env`
2. Run the compose project:
```Bash
docker compose -f dev.docker-compose.yml up -d
```
3. Run migrations (updates the database table structure): 
```Bash
docker compose -f dev.docker-compose.yml exec web python manage.py migrate
```
4. Run create static files command:
```Bash
docker compose -f dev.docker-compose.yml exec web python manage.py collectstatic
```
5. Make your changes
6. Restart and rebuild
```Bash
docker compose -f dev.docker-compose.yml down --rmi local web && docker compose -f dev.docker-compose.yml up -d
```
or
```Bash
docker compose -f dev.docker-compose.yml up --force-recreate --build -d
```

## Docker (dev containers)

Plugin link [click here](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

*Will follow soon*

## Python (standalone)

*Will follow soon*