---
title: VSCode Server
tags:
  - service
  - development
  - custom-server
status: active
---

# VSCode Server

VSCode Server is a remote development environment running on the custom server. It allows for coding directly on the server via a web interface.

## Docker Compose Configuration

```yaml
version: '3'
services:
  vscode-server:
    image: codercom/code-server
    ports:
      - "8443:8443"
    volumes:
      - ./vscode-data:/data
    restart: unless-stopped
```

## Notes

- Access the VSCode Server interface via `https://<server-ip>:8443`.
- Ensure the `vscode-data` directory is backed up to preserve workspace settings and extensions.
