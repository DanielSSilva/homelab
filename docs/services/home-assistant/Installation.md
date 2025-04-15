# Installation

## Reasoning

I'm currently running Home Assistant on my [Mac Mini M4](../../servers/Mac%20Mini%20M4/Mac%20Mini%20M4.md). Before owning this mac, I was running Home Assistant on my [Custom Server (Olympus)](../Custom%20Server%20(Olympus).md) on a dedicated VM under Unraid. However, because this server was being used for everything on my homelab, from experiments to "production" usage, this meant that from time to time my Home Assistant would go down: either because server ran out of memory, or because I crashed it so hard I had to hard reboot it, etc.

While running it on the Mac Mini still has its challenges (see [UTM](../../servers/Mac%20Mini%20M4/UMT.md) and [Problems File Vault](../../servers/Mac%20Mini%20M4/Problems%20File%20Vault.md), for my use case it's better than hosting it on my Unraid Instance. Maybe in the future I'll have a dedicated machine just for Home Assistant, but for now, this is the best solution I have.

## Running on Docker?
Although I'm aware that there are ways to run Home Assistant on containers, there are also some limitations. For example, I would need to maintain HA Core, Hypervisor and so on as different containers. There's also issues with USB devices not being passed through to the container. I would also lose features like Addons, so I think this is the best compromise for me.