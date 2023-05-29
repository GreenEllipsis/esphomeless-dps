# esphomeless-dps

![GitHub actions](https://github.com/GreenEllipsis/esphomeless-dps/actions/workflows/ci.yaml/badge.svg)
![GitHub stars](https://img.shields.io/github/stars/GreenEllipsis/esphomeless-dps)
![GitHub forks](https://img.shields.io/github/forks/GreenEllipsis/esphomeless-dps)
![GitHub watchers](https://img.shields.io/github/watchers/GreenEllipsis/esphomeless-dps)
[!["Buy Me A Coffee"](https://img.shields.io/badge/buy%20me%20a%20coffee-donate-yellow.svg)](https://www.buymeacoffee.com/GreenEllipsis)

ESP component to monitor and control the RDTech Digital Control Power Supply (DPS) series via UART-TTL.  
Forked from [esphome-dps](https://github.com/syssi/esphome-dps) and stripped of its ESPHome dependencies.

## Supported devices

* DPS3005 Buck, 0-30V, 0-5A, 160W
* DPS5005 Buck, 0-50V, 0-5A, 250W
* DPH5005 Buck/Boost, 0-50V, 0-5A, 250W
* DPS5015 Buck, 0-50V, 0-15A, 750W
* DPS5020 Buck, 0-50V, 0-20A, 1000W (tested by [@romeox44](https://github.com/syssi/esphome-dps/discussions/1))
* DPS8005 Buck, 0-80V, 0-5.1A, 408W

## Requirements

* Generic ESP32 or ESP8266 board

## Schematics

```

┌──────────┐                ┌─────────┐
│          │<----- RX ----->│         │
│ DPS5020  │<----- TX ----->│ ESP32/  │
│          │<----- GND ---->│ ESP8266 │<-- 3.3V
│          │                │         │<-- GND
└──────────┘                └─────────┘



│            o GND ── GND                │
│            o TXD ── GPIO5 (`rx_pin`)   │
│            o RXD ── GPIO4 (`tx_pin`)   │
│            o VCC                       │
└─[oooooooo]─────────────────[oooooooo]──┘

```

The connector is a 4 Pin GH Molex Pico 1.25mm. Do not connect the ESP to the VCC pin of the DPS in any case. [This will destroy the voltage regulator of the device](https://tech.scargill.net/dps5020-diy-power-supply/#comment-60544).

## Installation


## Example response 

```
```

## Known issues

Work in progress. There are surely lots of issues.

## Debugging

If this component doesn't work out of the box for your device please update your configuration to enable debug output and increase the log level to the see outgoing and incoming serial traffic

## References

* https://sigrok.org/wiki/RDTech_DPS_series
* https://github.com/rfinnie/rdserialtool
* https://github.com/AntaresAdroit/RDTech_PS_Comm
* https://github.com/syssi/esphome-dps
