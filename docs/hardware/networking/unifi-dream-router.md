---
title: Unifi
---

I wanted a way to separate my devices into multiple vlans. Since network is usually a rather complicated topic, my main requisite was that I could have a friendly, simple interface to configure everything. Unifi kept popping up as the go-to solution, with products that range from entry-level to enterprise-grade. I decided to go with the entry-level products, as I don't need anything too fancy.

# Dream Router
This is the brains of my network. I have the first version that was released (as the time of writing they've released the new Dream Router 7). It's a router that's bridged with my ISP's (since I'm forced to use the ISP's router 😒). It has 4 Ethernet Ports, where 2 of them support PoE, and it also has a built-in access point.

It serves my needs, but I do wish it had a bit more bandwith support. Although I have 1Gbps internet, the router's CPU is the bottleneck, and limits to ~600Mbps. This also happens because I have things like `Active Detections` and `Intrusion Prevention` enabled, which affect the CPU. 

[Reference](https://techspecs.ui.com/unifi/cloud-gateways/udr?subcategory=all-cloud-gateways)

# U6 In-Wall
This is a wall-mounted access point with 4 Ethernet ports, with one supporting PoE. They are also PoE powered, so I could easily use one of Dream Router's PoE port to power it. 

[Reference](https://eu.store.ui.com/eu/en/category/wifi-wall/products/u6-iw)

# Mini flex switch
