In short: best bang for the buck for AI operations, with the added bonus of being able to serve other functions, when compared to a graphics card.
I've started to explore AI more and more. I started by plugging my old GTX 1060 into my server, but it drew 120W when I queried LLMs, without a big performance. I then considered upgrading my desktop's GPU to something like a 4070 and move the 3060 to my server, but only that was more expensive, but it would also draw much more power. Upon reading, searching and watching videos, I found out that the M4 chip is the perfect compromise for my case for power usage vs LLM performance

# Hardware Specifications

| Component              | Specification                                      |
|------------------------|---------------------------------------------------|
| **Chip**              | 10-core CPU, 10-core GPU, and 16-core Neural Engine |
| **Memory**            | 16GB unified memory                               |
| **Storage**           | 256GB SSD                                         |
| **Connections and Expansion** | 5 USB-C ports, Gigabit Ethernet port, 3.5 mm headphone jack|

## Power Management
- Has UPS connected to it, which is configured to shut down the Mac Mini when the battery reaches a certain percentage.
- Set to boot up when power is restored after a power outage.
- **Power Consumption**: [According to Apple](https://support.apple.com/en-us/103253) it idles at 4W, and at max it draws 65W. For comparison, my [Custom Server - Olympus](../Custom%20Server%20-%20Olympus.md) draws 60W on idle.

# Role in Homelab

- AI
    - [Ollama](../../services/Ollama.md) & OpenWebUI
- Media
    - Jellyfin
- Host critical services
    - Pihole
    - [Home Assistant](../../services/home-assistant/Home%20Assistant.md)