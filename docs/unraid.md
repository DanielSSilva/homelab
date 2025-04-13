---
title: Unraid
---

# Unraid

This page documents my Unraid setup, which serves as the foundation for much of my homelab.

## Overview

[Brief description of what Unraid is and why you chose it]

## Hardware Configuration

| Component | Specification | Notes |
|-----------|---------------|-------|
| CPU | [CPU Model] | [Any specific CPU settings] |
| RAM | [Amount/Type] | [ECC? Timings?] |
| Storage Array | [Drive listing] | [Array configuration] |
| Cache Drives | [SSD/NVMe model(s)] | [Pool configuration] |
| Parity Drives | [Drive models] | [Single/Dual parity?] |
| Network | [NIC hardware] | [Link aggregation?] |

## Unraid Configuration

- **Version**: [Current Unraid version]
- **Registration Key**: [Key type - Basic/Plus/Pro]
- **Uptime Stats**: [Typical uptime/reboot frequency]

## Storage Shares

| Share Name | Purpose | Disk Policy | Access Control |
|------------|---------|-------------|----------------|
| Media | Movies, TV Shows | Use cache: Yes | SMB, NFS |
| Backups | System backups | Use cache: No | SMB |
| [Other shares] | | | |

## Docker Configuration

- **Docker Path**: [Path to Docker data]
- **Network Type**: [Bridge/Host/Custom]
- **Image Location**: [Storage location]

## VM Configuration

- **CPU Isolation**: [CPUs reserved for VMs]
- **Memory Allocation**: [RAM reserved]
- **VM storage**: [VDisk location]
- **Active VMs**: 
  - [VM 1]: [Purpose, resources]
  - [VM 2]: [Purpose, resources]

## Plugins Installed

| Plugin | Version | Purpose |
|--------|---------|---------|
| Dynamix System Stats | [version] | System monitoring |
| [Other plugins] | | |

## Backup Strategy

- **Array Data**: [How array data is backed up]
- **Appdata**: [How docker data is backed up]
- **System Config**: [Unraid config backup]
- **Schedule**: [Backup frequency]

## Maintenance Procedures

- **Parity Checks**: [Frequency and schedule]
- **Array Operations**: [How array operations are scheduled]
- **Update Process**: [Update procedures and testing]
- **Monitoring**: [How system is monitored]