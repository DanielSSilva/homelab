# Software

## Brew
Installed through their [official docs](https://brew.sh/)

## Colima
Colima is a container runtime that runs on top of Docker. It provides a lightweight and efficient way to run containers, especially on macOS. This means that I don't need to install Docker Desktop to be able to run docker.

### Installation
```shell
brew install colima

# Set colima to start when system boots
brew services start colima
```

## Docker & Docker-Compose
Docker is the container runtime that I use to run most of my services. 
### Installation
```shell
brew install docker
brew install docker-compose
```

## UMT
> UTM employs Apple's Hypervisor virtualization framework to run ARM64 operating systems on Apple Silicon at near native speeds.

Since I'm running [Home Assistant](../../services/Home%20Assistant.md)  on this mac, I needed a way to run it in a VM. I've decided to try UTM, as it seems to be optimized especially for the M series macs.

### Installation
I installed it through the [official website](https://mac.getutm.app/)

