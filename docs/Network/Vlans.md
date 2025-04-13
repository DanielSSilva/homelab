My main reason for setting up Unifi is the fact that it allows me to segregate my network into multiple smaller ones. The goal of this approach is to have more control over my network by defining which devices/networks can communicate with each other.

# Trusted Network
The rule for this network is that only trusted, known devices have access. Devices like my phone, server, and desktop are included here. This network can see and access all other networks.

# IoT Network
Devices on this network are those that require internet access but are not fully trusted since they are cloud-based and not entirely under my control. Examples include:
- Xiaomi cameras
- Google devices such as Google Mini or Google Nest
- Smart vacuum cleaner

This network is isolated to itself, meaning it cannot see or access devices on other networks, except for Home Assistant, which is hosted on the Trusted Network. This exception is IP-based.

# Local-Only Network
This network is for devices that need to communicate within my network but do not require internet access to function. Examples include:
- Reolink cameras
- Shelly devices

This network follows the same philosophy as the IoT Network, where devices cannot see or access devices on other networks, except for Home Assistant.

# Guest Network
This is the most restrictive network setup. Devices on this network cannot see anything else—not even other devices on the same network. This is the network I use for guests.