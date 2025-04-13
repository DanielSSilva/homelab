---
title: Frigate
tags:
  - service
  - surveillance
  - custom-server
status: active
---

# Frigate

Frigate is an open-source NVR (Network Video Recorder) with real-time AI object detection, running on the custom server.

## Docker Compose Configuration

```yaml
version: '3'
services:
  frigate:
    image: blakeblackshear/frigate
    ports:
      - "5001:5000"
    volumes:
      - ./frigate-config:/config
      - ./frigate-media:/media
    restart: unless-stopped
```

## Notes

- Frigate integrates with Home Assistant for advanced automation.
- The `frigate-config` directory contains configuration files, and `frigate-media` stores recorded footage.
