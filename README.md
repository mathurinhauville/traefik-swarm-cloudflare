# Traefik 3 in Docker Swarm Mode with Let's Encrypt and Cloudflare

This is an example of how to use Traefik in Docker Swarm Mode with Let's Encrypt and Cloudflare. This projet is based on [this video](https://youtu.be/n1vOfdz5Nm8?si=VoW1PGYp0LKy3pam) from [@Techno Tim](https://github.com/timothystewart6). 
It's just refactored to use in Docker Swarm Mode.

## Prerequisites

Watch the [video](https://youtu.be/n1vOfdz5Nm8?si=VoW1PGYp0LKy3pam) to understand the concepts and the configuration and leave a like ;)

## How to use

```bash
docker swarm init
````

```bash
docker network create -d overlay proxy
```

```bash
cd traefik
docker stack deploy -c traefik.yml traefik -d
```

```bash
cd my-service
docker stack deploy -c my-service.yml my-service -d --with-registry-auth
```
