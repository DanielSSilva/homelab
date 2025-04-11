# Home Assistant Sensors

This page documents the sensors integrated with my Home Assistant setup.

## Door Sensors

| Location | Type | Connection | Purpose |
|----------|------|------------|---------|
| Front Door | [Brand/Model] | [Zigbee/Z-Wave/etc.] | Security monitoring |
| [Other doors] | | | |

### Configuration Details

```yaml
# Example configuration entry for door sensors
binary_sensor:
  - platform: [platform]
    name: "Front Door"
    device_class: door
    # Additional configuration...
```

## Temperature Sensors

| Location | Type | Connection | Accuracy |
|----------|------|------------|----------|
| Living Room | [Brand/Model] | [Connection type] | ±0.5°C |
| [Other locations] | | | |

### Configuration Details

```yaml
# Example configuration entry for temperature sensors
sensor:
  - platform: [platform]
    name: "Living Room Temperature"
    device_class: temperature
    unit_of_measurement: "°C"
    # Additional configuration...
```

## Motion Sensors

| Location | Type | Connection | Detection Range |
|----------|------|------------|----------------|
| Hallway | [Brand/Model] | [Connection type] | [Range] |
| [Other locations] | | | |

## Sensor Automations

Examples of automations using these sensors:

```yaml
# Example automation triggered by sensors
automation:
  - alias: "Notify when front door opens"
    trigger:
      platform: state
      entity_id: binary_sensor.front_door
      to: "on"
    action:
      service: notify.mobile_app
      data:
        message: "Front door opened"
```

## Sensor Maintenance

- Battery replacement schedule
- Typical issues and troubleshooting
- Calibration procedures (if applicable)