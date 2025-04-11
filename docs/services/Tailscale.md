---
title: Tailscale
tags:
  - service
  - networking
  - vpn
  - mac-mini
  - custom-server
  - both
status: active
---

# Tailscale

This page documents my Tailscale setup, which provides secure networking between my devices and homelab.

## Overview

Tailscale is a zero-config VPN that makes the devices and applications I use feel like they're on the same secure network, regardless of location.

## Installation Locations

| Device/System | Installation Method | Version | Purpose |
|---------------|---------------------|---------|---------|
| Primary Server | [Install method] | [Version] | Main homelab access |
| Mac Mini | [Install method] | [Version] | Development machine access |
| Mobile Devices | [Install method] | [Version] | Remote monitoring |
| [Other devices] | [Install method] | [Version] | [Purpose] |

## Network Configuration

- **Tailnet Name**: [Your Tailnet name]
- **Subnet Routes**: [Subnets advertised]
- **Exit Node Configuration**: [Whether exit nodes are enabled]
- **DNS Configuration**: [MagicDNS/custom settings]

## Access Controls

Description of ACL policies implemented:

```json
// Example ACL policy
{
  "acls": [
    {
      "action": "accept",
      "users": ["*"],
      "ports": ["*:*"]
    }
  ]
}
```

## Key Features In Use

- **Tailscale SSH**: [Enabled/Disabled, configuration]
- **Funnel**: [How Funnel is used, if applicable]
- **Device Groups**: [How devices are grouped]
- **Tags**: [Tags used to organize devices]

## Services Accessed via Tailscale

| Service | Access Method | Authentication | Notes |
|---------|---------------|----------------|-------|
| Home Assistant | Direct access | Normal HA auth | Only accessible via Tailscale |
| [Other service] | [Access method] | [Auth method] | [Notes] |

## Security Considerations

- Multi-factor authentication configuration
- Device approval process
- Key rotation policy
- Access review process

## Troubleshooting

Common issues and solutions:

- Connectivity problems
- Device authorization issues
- Performance considerations