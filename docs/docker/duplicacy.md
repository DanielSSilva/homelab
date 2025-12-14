# Duplicacy

## What is it?

_Duplicacy backs up your files to many cloud storages with client-side encryption and the highest level of deduplication_
&emsp;&emsp;

\- [Source](https://duplicacy.com/)

## Docker Compose

```yaml
networks:
  proxy:
    external: true
    name: proxy
services:
  duplicacy:
    image: saspus/duplicacy-web:latest
    container_name: duplicacy
    hostname: duplicacy-unraid
    networks:
      - proxy
    restart: unless-stopped
    ports:
      - 3875:3875
    environment:
      - USR_ID=0
      - GRP_ID=0
      - TZ=Europe/Lisbon
    volumes:
      - ${APPDATA_DIR}/duplicacy/config:/config
      - ${APPDATA_DIR}/duplicacy/logs:/logs
      - /mnt/user/duplicacy_cache:/cache
      - /mnt/user/homelab/appdata_backups:/unraid_shares/appdata_backups:ro
      - ${APPDATA_DIR}/immich/:/unraid_shares/immich
    labels:
      - traefik.enable=true
      - traefik.http.routers.duplicacy.entryPoints=https
      - traefik.http.routers.duplicacy.rule=Host(`backups.${DOMAIN_BASE_URL}`)
      - net.unraid.docker.icon=https://raw.githubusercontent.com/selfhosters/unRAID-CA-templates/master/templates/img/duplicacy.png
```

## References
- [Official Website](https://duplicacy.com/)
- [Documentation](https://duplicacy.com/guide.html)
- [GitHub Repository](https://github.com/gilbertchen/duplicacy)