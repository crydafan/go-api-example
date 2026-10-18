# Go API example

A small HTTP API built with the Chi router.

## Endpoints

- `GET /healthz` returns `204 No Content` for container and platform health checks.
- `GET /api/hello?name=Codex` returns `{"message":"Hello, Codex!"}`. The `name` query parameter is optional and defaults to `world`.

The server listens on port `8080` by default. Set `PORT` to change it.

## Run locally

```sh
go run .
```

Then try `curl http://localhost:8080/api/hello?name=Codex`.

## Build and run with Docker

```sh
docker build -t go-api-example .
docker run --rm -p 8080:8080 go-api-example
```

The image uses a multi-stage build and runs the compiled API as an unprivileged user.
