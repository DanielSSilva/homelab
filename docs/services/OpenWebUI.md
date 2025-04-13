---
title: OpenWebUI
tags:
  - service
  - chat
  - mac-mini
status: active
---

# OpenWebUI

OpenWebUI is a chat interface service running on the Mac Mini M4. It provides a user-friendly interface for interacting with AI models.

## Docker Compose Configuration

```yaml
version: '3'
services:
  openwebui:
    image: openwebui/openwebui
    ports:
      - "8080:8080"
    volumes:
      - ./openwebui-data:/data
    restart: unless-stopped
```

## Notes

- OpenWebUI integrates seamlessly with Ollama for AI model interactions.
- The service is accessible via `http://localhost:8080` when running locally.
