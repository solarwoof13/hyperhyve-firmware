# Hyper Hyve — Firmware

Device firmware for all Hyper Hyve smart hive products.

## Structure
```
shared/
  cellular/     ← SIM7000G LTE-M connection, AT commands
  mqtt/         ← MQTT publish/subscribe to AWS IoT Core
  sensors/      ← Shared sensor drivers (BME688, INMP441, LIS3DH)
  power/        ← Deep sleep, solar/battery management
hive-top/       ← Hyve Top (Phase 1) — ESP32 + SIM7000G
hhpro-v1/       ← HH Pro full hive (Phase 2)
hhcom-v1/       ← HH Commercial (Phase 3)
```

## Hardware (Hive Top)
- **MCU + Cellular + GPS:** LilyGO T-SIM7000G (ESP32 + SIM7000G)
- **Environmental:** BME688 (temp, humidity, pressure, VOC)
- **Acoustic:** INMP441 I2S MEMS microphone
- **Motion:** LIS3DH accelerometer
- **Power:** 18650 cell + dual 5V 1W solar panels
- **Identity:** NTAG 424 DNA NFC tag + HH-XXXXXX pressed metal serial

## Data Plan
- 1NCE SIM — $14 one-time, 10 years, 500MB
- LTE-M / NB-IoT global

## Sensor Publish Rate
- Normal: every 5 minutes
- Alert condition: every 60 seconds
- Deep sleep between transmissions
