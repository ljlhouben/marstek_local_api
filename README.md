This project is a fork of the original ['Marstek Energy Storage - Home Assistant Integration (Proof of Concept)'](https://github.com/lemuba/Marstek-Energy-Storage---Home-Assistant-Custom-Integration---Proof-of-Concept) by `Lemuba`

# Marstel Local API - Home Assistant Custom Integration
> **Version:** '0.0.0' · **Domain:** `marstek_local_api` · **IoT class:** `local_polling`

Is a lightweight local integration for Marstek energy storage systems (UDP-JSON).
It retrieves status data and allows switching between operating modes.

## ⚠️ **The project is in development** ⚠️

**IMPORTANT:**\
Please note that I´m a PLC programmer and do not have much experience with Python and Home-Assistant. 
From time to time I will spend some time to get it working on my own Home-Assistant server. Some sensors, switches,
or features may not work reliably. That is why I will **not provide support**, and I will **not guarantee compatibility or functionality**.
Many thanks to everyone who will be testing, contribute, or provided feedback — it will be appreciated! 🫶

The code will be tested with my own devices **Marstek Venus E v1** and **Marstek Venus E v2** with **API enabled on port 30000**

### Release History:
> **Version:** 0.0.0 ![Status: Copy](https://img.shields.io/badge/Status-COPY-lightgray)
> - Copy of original sources from 'Lemuba'
> ---
> **Version:** 0.1.0 ![Status: Open](https://img.shields.io/badge/Status-OPEN-lightblue)
> - Scope T.b.d.
------------------------------------------------------------------------

## ✨ Features

-   **Sensors**: SoC, battery/PV/grid power, energy counters, etc.
-   **Control operating mode**: `Auto`, `AI`, `Manual`, `Passive`
-   **Switch/Select entities** for quick mode switching

------------------------------------------------------------------------

## 📦 Installation / 📂 Project Structure 

1.  Create the folder `custom_components/marstek_local_api` in your Home Assistant `config` directory.
2.  Copy all contents of this repository into that folder.
3.  Restart Home Assistant.

```
custom_components/marstek/
    ├── __init__.py            # Setup, initialization
    ├── api.py                 # UDP client (ES.GetStatus / ES.GetMode / ES.SetMode / Bat.GetStatus)
    ├── coordinator.py         # DataUpdateCoordinator with retry/smoothing
    ├── sensor.py              # Dynamic + fixed battery sensors
    ├── switch.py              # Mode switches
    ├── number.py              # Passive power/countdown controls
    ├── select.py              # Operating mode selection
    ├── binary_sensor.py       # Charge/discharge allowed
    ├── manifest.json          # Metadata: domain, name, version, iot_class, config_flow
    ├── diagnostics.py         # HA diagnostics integration
    ├── strings.json           # String resources
    ├── translations/\
    │   └── en.json            # Language support
```
👉 The folder name must be exactly `marstek_local_api`, otherwise Home Assistant
will not detect the integration.

------------------------------------------------------------------------

## ⚙️ Setup (UI)

Go to: **Settings → Devices & Services → Add Integration → "Marstek Local API"**,
then enter:
-   **Port** (default: `30000`)\
-   **T.B.D**

------------------------------------------------------------------------

## 🧩 Entities

### Sensors
-   Battery SoC (`bat_soc`)
-   Battery Power, PV Power, Grid Import/Export Power
-   Energy counters (PV, grid, load, battery)
-   Battery temperature, capacity, rated capacity

### Switches
-   Quick selectors for modes (`Auto`, `AI`, `Manual`, `Passive`)

------------------------------------------------------------------------

## 🔌 Network & Protocol
-   Uses **UDP** to communicate with the battery (default port 30000)\
-   Configurable retries and smoothing

------------------------------------------------------------------------

## 🛠 Troubleshooting

-   **No data?** Check IP/port/device ID and ensure the device is
    reachable\

------------------------------------------------------------------------

## 📜 License & Maintainer

-   **Maintainer:** `ljlhouben` 
-   MIT License

------------------------------------------------------------------------

**Toi Toi Toi** 🫣 \
👋 Cheers Ludo
