# shiny-auth-2

![](figures/post_image.png)

Companion repo for part 2 of the shiny auth series. Refer to the [blog post](https://blog.gilakl.com/r-shiny-auth-ii/) for an overview of the contents of this repo.

## Building and deploying

There are a few steps to follow to deploy this stack.

* Start a new docker network

```bash
docker stack deploy traefik-network -c ./config/traefik/traefik-network.yml
```

* Deploy the new traefik instance

```bash
docker stack deploy traefik -c ./config/traefik/traefik.yml
```

* Deploy the shiny application

```bash
docker stack deploy shiny-auth -c ./config/shiny-auth/docker-compose.yml
```