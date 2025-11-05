# twix-feeder
Smart ESP32 cat feeder for Home Assistant
# 🐱 Twix Feeder System
Smart ESP32-powered pet-feeder with Home Assistant automation, scheduling, and mobile dashboard.

---

## ⚙️ Components

| Layer | File | Purpose |
|-------|------|----------|
| Firmware | [`esphome/twix_feeder_device_template.yaml`](esphome/twix_feeder_device_template.yaml) | Pre-configured ESP32 firmware with captive-portal Wi-Fi setup |
| HA Package | [`homeassistant/packages/twix_feeder_core.yaml`](homeassistant/packages/twix_feeder_core.yaml) | Helpers, daily counter, and manual-feed scripts |
| Blueprint | [`blueprints/automation/pricklyguy/twix_feeder_slot.yaml`](blueprints/automation/pricklyguy/twix_feeder_slot.yaml) | Schedulable feed automation |
| Dashboard | [`dashboard/twix_mobile.yaml`](dashboard/twix_mobile.yaml) | Mobile control panel UI |

---

## 🧩 Install the Blueprint

Click this link in Home Assistant:

👉 [Import Twix Feeder Blueprint](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://raw.githubusercontent.com/ogbulldog50/twix-feeder/main/blueprints/automation/pricklyguy/twix_feeder_slot.yaml)

Then create four automations (Slot 1–4) and select:
- `input_boolean.feed_slot#_enabled`
- `input_datetime.feed_slot#_time`
- `input_number.feed_slot#_portions`
- Your ESPHome `number.twix_feeder_ha_target_pulses`
- Your ESPHome `button.twix_feeder_execute_feed_action`
- Optional: `script.twix_play_chowtime`

---

## 🐾 Flash the ESP32

Flash the pre-configured firmware via ESPHome Web:

👉 [Flash Twix Feeder Firmware](https://web.esphome.io/?dashboard=https://github.com/pricklyguy/twix-feeder/blob/main/esphome/twix_feeder_device_template.yaml)

After flashing:
1. Connect to the **Twix Feeder Setup** Wi-Fi AP.  
2. Enter your home Wi-Fi credentials.  
3. The device will auto-connect and appear in ESPHome & Home Assistant.

---

## 📱 Dashboard (Optional)

Add the dashboard file to your dashboard YAML or copy its contents into a new view:

[`dashboard/twix_mobile.yaml`](dashboard/twix_mobile.yaml)

---

## 🪪 License
MIT License © 2025 Prickly Guy Creations
