# Frigate

## What is it?

_Frigate is an open source NVR built around real-time AI object detection. All processing is performed locally on your own hardware, and your camera feeds never leave your home._

&emsp;&emsp;\- [Source](https://frigate.video/)

## Docker Compose

```yaml
networks:
   proxy:
     external: true

services:
  frigate:
    container_name: frigate
    image: ghcr.io/blakeblackshear/frigate:stable
    restart: always
    shm_size: 512mb
    networks:
      - proxy
    ports:
      - 8971:8971 # Authenticated UI & API
      - 8554:8554 # RTSP restream
      - 5000:5000 # Internal UI/API (unauthenticated)
      - 8555:8555/tcp # WebRTC TCP
      - 8555:8555/udp # WebRTC UDP
      - 1984:1984 #go2rtc ui
    volumes:
      - ${APPDATA_DIR}/frigate:/config
      - /mnt/cache/frigate_media:/media/frigate
      - /etc/localtime:/etc/localtime
    environment:
      - FRIGATE_RTSP_PASSWORD=${FRIGATE_RTSP_PASSWORD}
    labels:
      - traefik.enable=true
      - traefik.http.services.frigate.loadbalancer.server.port=5000
      - traefik.http.routers.frigate.entryPoints=https
      - net.unraid.docker.icon=https://raw.githubusercontent.com/yayitazale/unraid-templates/main/frigate.png
```

## .env
```env
FRIGATE_RTSP_PASSWORD=your_rtsp_password_here
```

## References
- [Official Website](https://frigate.video/)
- [Documentation](https://docs.frigate.video/)
- [GitHub Repository](https://github.com/blakeblackshear/frigate)