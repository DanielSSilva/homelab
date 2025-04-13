
## Hardware Specifications

| Component | Details | Notes |
|-----------|---------|-------|
| CPU/Processor | AMD Ryzen [model] | [Notes] |
| Memory/RAM | 32GB DDR4 | [Notes] |
| Storage | 2TB NVMe + 8TB HDD | [Notes] |
| Networking | 2.5GbE NIC | [Notes] |
| Other Components | [Additional hardware] | [Notes] |

## Role in Homelab

This server is responsible for:

- Main storage and virtualization host
- Media streaming and management
- Network services and automation

## Operating System

- **OS**: Unraid
- **Version**: [version]
- **Update Strategy**: [How updates are managed]

## Network Configuration

- **Hostname**: homeserver
- **IP Address**: [IP configuration]
- **Network Role**: [Network functions]

## Services Hosted

<!-- Manual service list -->
| Service | Type | Resource Usage | Dependencies |
|---------|------|---------------|--------------|
| Unraid | Bare metal | High | None |
| Docker | Platform | Medium | Unraid |

<!-- Dynamic service list based on tags -->
### Services Running on This Hardware

This section is automatically generated based on documentation tags.

[TAGS=custom-server]

## Maintenance Procedures

- Weekly array check
- Monthly plugin updates

## Monitoring

- **Monitoring Tools**: Grafana, Prometheus
- **Critical Metrics**: Disk health, CPU temperature
- **Alerts**: Email notifications

## Backup Strategy

- **What's Backed Up**: Appdata, configuration files
- **Backup Method**: Snapshot and offsite replication
- **Schedule**: Daily incremental, weekly full

## Related Documentation

- [Link to related docs]

## Change History

| Date | Change | Reason |
|------|--------|--------|
| April 11, 2025 | Initial documentation | Setting up homelab documentation |