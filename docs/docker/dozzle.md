# Dozzle

_Dozzle is a small lightweight application with a web based interface to monitor Docker logs. It doesn’t store any log files. It is for live monitoring of your container logs only._

&emsp;&emsp;\- [Source](https://github.com/amir20/dozzle?tab=readme-ov-file#dozzle---dozzledev)

## Docker Compose

```yaml
networks:
  proxy:
    external: true
services:
    image: amir20/dozzle:latest
    container_name: dozzle
    environment:
      DOCKER_HOST: tcp://dockersocket:2375
    ports:
      - 8099:8080
    networks:
      - proxy
    labels:
      net.unraid.docker.icon: https://github.com/amir20/dozzle/blob/master/public/favicon.png?raw=true
      traefik.enable: true
      traefik.http.routers.dozzle.entrypoints: https
      traefik.http.routers.dozzle.rule: Host(`logs.${DOMAIN_BASE_URL}`)
```

## References

- [Official Website](https://dozzle.dev/)

- [GitHub Repository](https://github.com/amir20/dozzle)