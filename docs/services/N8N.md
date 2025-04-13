---
title: N8N
tags:
  - service
  - automation
  - custom-server
status: active
---

# N8N

N8N is a workflow automation tool running on the custom server. It allows for creating and managing automated workflows.

## Docker Compose Configuration

```yaml
version: '3'
services:
  n8n:
    image: n8nio/n8n
    ports:
      - "5678:5678"
    volumes:
      - ./n8n-data:/data
    restart: unless-stopped
```

## Notes

- N8N provides a visual interface for creating workflows and integrations.
- Ensure the `n8n-data` directory is backed up to preserve workflows and configurations.
