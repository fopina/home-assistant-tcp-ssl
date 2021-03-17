# TCP-ssl

Custom version of [tcp core sensor](https://github.com/home-assistant/core/blob/dev/homeassistant/components/tcp/sensor.py) to add SSL support

## Setup
There are two ways to set up:

#### 1. Using HACS (preferred)
Add this repository as custom repository to Home Assistant Community Store HACS (https://hacs.xyz/) and then search for `TCP SSL`.

If you use this method, your component will always update to the latest version. But you'll need to set up HACS first.

#### 2. Manual
Copy all files from custom_components/tcp_ssl to a `<ha_config_dir>/custom_components/tcp_ssl` directory

If you use this method then you'll need to keep an eye on this repository to check for updates.

## Usage

```yaml
sensor:
  - platform: tcp_ssl
    name: testhtml
    host: google.com
    port: 443
    payload: |+
      GET / HTTP/1.1
      Host: google.com

    buffer_size: 15
    timeout: 10
    scan_interval: 10
    ssl: on
```
