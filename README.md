# ESP32 Wi-Fi Node Reference Firmware v0.2.0

This project extends v0.1.0 by adding MQTT and ThingsBoard telemetry.

## Configure

Edit `include/config.h`:

```cpp
constexpr const char* WIFI_SSID = "YOUR_WIFI_SSID";
constexpr const char* WIFI_PASSWORD = "YOUR_WIFI_PASSWORD";
constexpr const char* THINGSBOARD_HOST = "thingsboard.cloud";
constexpr uint16_t THINGSBOARD_PORT = 1883;
constexpr const char* THINGSBOARD_ACCESS_TOKEN = "YOUR_DEVICE_ACCESS_TOKEN";
```

ThingsBoard MQTT access-token mode:

```text
MQTT username = device access token
MQTT password = empty
```

Telemetry topic:

```text
v1/devices/me/telemetry
```

## Added Files

```text
include/mqtt_client.h
src/mqtt_client.cpp
include/telemetry.h
src/telemetry.cpp
```

## Serial Commands

```text
help      - show this help
status    - print Wi-Fi, MQTT, RSSI, and uptime status
mqtt      - print MQTT status
publish   - publish telemetry immediately
event     - publish a test event immediately
rssi      - print current RSSI
reconnect - force Wi-Fi and MQTT reconnect
version   - print firmware version
```

## Telemetry Keys

- `device_id`
- `firmware_version`
- `rssi_dbm`
- `signal_quality`
- `wifi_connected`
- `mqtt_connected`
- `wifi_state`
- `mqtt_state`
- `wifi_reconnect_count`
- `mqtt_reconnect_count`
- `mqtt_publish_success_count`
- `mqtt_publish_fail_count`
- `uptime_s`
- `free_heap`
- `event`
- `severity`
- `message`
