---
title: Mac Mini M4
---

# Why a Mac Mini M4?

In short: best bang for the buck for AI operations, with the added bonus of being able to serve other functions, when compared to a graphics card.
I've started to explore AI more and more. I started by plugging my old GTX 1060 into my server, but it drew 120W when I queried LLMs, without a big performance. I then considered upgrading my desktop's GPU to something like a 4070 and move the 3060 to my server, but only that was more expensive, but it would also draw much more power. Upon reading, searching and watching videos, I found out that the M4 chip is the perfect compromise for my case for power usage vs LLM performance

## Hardware Specifications

| Component              | Specification                                      |
|------------------------|---------------------------------------------------|
| **Chip**              | 10-core CPU, 10-core GPU, and 16-core Neural Engine |
| **Memory**            | 16GB unified memory                               |
| **Storage**           | 256GB SSD                                         |
| **Connections and Expansion** | 5 USB-C ports, Gigabit Ethernet port, 3.5 mm headphone jack|

## Role in Homelab

- AI
    - Ollama & OpenWebUI
- Media
    - Jellyfin
- Host critical services
    - Pihole
    - Home Asisstant

## Power Management
- Has UPS connected to it, which is configured to shut down the Mac Mini when the battery reaches a certain percentage.
- Set to boot up when power is restored after a power outage.
- **Power Consumption**: [According to Apple](https://support.apple.com/en-us/103253) it idles at 4W, and at max it draws 65W. For comparison, my [[Custom Server - Olympus]] draws 60W on idle.

## Software

### Brew
Installed through their [official docs](https://brew.sh/)

### Colima
Colima is a container runtime that runs on top of Docker. It provides a lightweight and efficient way to run containers, especially on macOS. This means that I don't need to install Docker Desktop to be able to run docker.

#### Installation
```shell
brew install colima

# Set colima to start when system boots
brew services start colima
```

### Docker & Docker-Compose
Docker is the container runtime that I use to run most of my services. 
#### Installation
```shell
brew install docker
brew install docker-compose
```

### UMT
> UTM employs Apple's Hypervisor virtualization framework to run ARM64 operating systems on Apple Silicon at near native speeds.

Since I'm running [Home Assistant](../services/home-assistant/index.md)  on this mac, I needed a way to run it in a VM. I've decided to try UTM, as it seems to be optimized especially for the M series macs.

#### Installation
I installed it through the [official website](https://mac.getutm.app/)

