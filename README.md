# KNX Intelligent Light Control Blueprint for Home Assistant

[![Home Assistant](https://img.shields.io/badge/Home%20Assistant-Blueprint-41BDF5.svg)](https://www.home-assistant.io/)
[![KNX](https://img.shields.io/badge/KNX-Integration-00A9E0.svg)](https://www.home-assistant.io/integrations/knx/)
[![Version](https://img.shields.io/badge/Version-1.1.0-blue.svg)](https://github.com/chrisrocks177/ha_intelligent_light_control/releases)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

[![Buy Me A Coffee](https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png)](https://www.buymeacoffee.com/chrisrocks)


Professional KNX light control with scene-based switching, toggle function, and intelligent day/night automation.

## 🎯 Key Features

- **3 KNX Buttons with Toggle Function**
  - 🔆 Day lighting
  - 🌙 Night lighting  
  - 🔄 Automatic day/night selection
  - Toggle: Pressing again turns off the active scene

- **Scene-Based Switching (NEW in v1.1.0)**
  - Only turns off lights that are part of the active scene
  - Solves the "shared lights" problem (light illuminates multiple rooms)
  - More precise and flexible than group-based switching

- **Optional Features**
  - ⏻ Fourth "All Off" button
  - 📡 KNX status feedback for button LEDs
  - 🚶 Passage lighting with presence sensor
  - ⏲️ 2-level long-term absence detection

## 📋 Requirements

- Home Assistant with [KNX Integration](https://www.home-assistant.io/integrations/knx/)
- Binary sensor for day/night detection (e.g. based on sun position)
- Scenes for day and night lighting
- Input Select Helper with options: `off`, `day`, `night`, `passage`

## 🚀 Installation

### Method 1: Import via URL (recommended)

1. Open Home Assistant
2. Go to **Settings** → **Automations & Scenes** → **Blueprints**
3. Click **Import Blueprint**
4. Paste this URL:
   ```
   https://github.com/chrisrocks177/ha_intelligent_light_control /blob/main/light_control_day_night_EN.yaml
   ```
5. Click **Preview** then **Import**

### Method 2: Manual Installation

1. Download the file `light_control_day_night_EN.yaml`
2. Copy it to your Home Assistant Blueprint directory:
   ```
   config/blueprints/automation/chrisrocks177/
   ```
3. Restart Home Assistant or reload Blueprints

## 📖 Quick Start

### 1. Create an Input Select Helper

Go to **Settings** → **Devices & Services** → **Helpers** → **Create Helper**

```yaml
Living Room Light Status:
  Options:
    - off
    - day
    - night
    - passage
```

### 2. Create Your Scenes

Example for day scene:
```yaml
scene.living_room_day:
  entities:
    light.living_room_ceiling:
      state: on
      brightness: 255
    light.living_room_floor_lamp:
      state: on
      brightness: 200
```

⚠️ **IMPORTANT:** Make sure ALL relevant lights are included in the scene!

### 3. Create Automation from Blueprint

1. Go to **Settings** → **Automations & Scenes**
2. Click **Create Automation** → **Use Blueprint**
3. Select "Light Control with Day and Night Mode"
4. Configure KNX group addresses and scenes

## 🔧 Configuration

### Required Fields

| Field | Description | Example |
|-------|-------------|---------|
| Button Day Lighting | KNX group address | `1/2/1` |
| Button Night Lighting | KNX group address | `1/2/2` |
| Button Automatic | KNX group address | `1/2/3` |
| Day/Night Sensor | Binary sensor | `binary_sensor.daytime` |
| Scene Day | Home Assistant scene | `scene.living_room_day` |
| Scene Night | Home Assistant scene | `scene.living_room_night` |
| Status Helper | Input Select | `input_select.lr_status` |
| Light Group | Light Group | `light.living_room` |

### Optional Fields

If you don't want to use a feature:
- **KNX group addresses:** Leave `31/7/255`
- **Entities:** Leave `sun.sun` selected

See documentation files for details on all fields.

## 💡 How It Works

### Toggle Logic

```
Press Button → Check Status
├─ Status = off → Activate Scene
├─ Status = active scene → Turn off scene lights
└─ Status = other scene → Activate Scene
```

### Scene-Based Switching

**Problem:** Shared lights
```
Ceiling light illuminates living room AND dining room
❌ Old system: Group-based → Light always turns off
✅ New system: Scene-based → Only when in scene
```

**Solution:**
1. Blueprint determines active scene
2. Reads light list from scene attributes
3. Only turns off these lights

## 📦 Supported Entities

The Blueprint supports for switching off:
- ✅ `light.*` - Lights
- ✅ `switch.*` - Switches
- ✅ `fan.*` - Fans
- ✅ `plug.*` - Plugs
- ✅ All entities with `turn_off` service

## 🐛 Troubleshooting

### Lights don't turn off with toggle

**Cause:** Lights missing in scene

**Solution:**
1. Open scene in Home Assistant
2. Check included entities
3. Add missing lights

### KNX button doesn't respond

**Checks:**
1. KNX integration running?
2. Group address correctly formatted? (X/Y/Z)
3. Button sending telegram? (Check KNX monitor)

### Passage lighting doesn't activate

**Checks:**
1. Presence sensor status correct?
2. Override entities at "off"?
3. KNX sensor follow-up time configured?

### Development Guidelines

- Code should follow Home Assistant Blueprint standards
- New features should be documented
- Changelog must be updated
- Tests for critical functions

## 📝 License

This project is licensed under the MIT License - see [LICENSE](LICENSE) file for details.

## 🙏 Credits

Developed for the Home Assistant Community with focus on professional KNX integration.

## 📞 Support

- **Issues:** [GitHub Issues](https://github.com/chrisrocks177/ha_intelligent_light_control /issues)
- **Discussions:** [GitHub Discussions](https://github.com/chrisrocks177/ha_intelligent_light_control /discussions)
- **Home Assistant Forum:** [Community Forum](https://community.home-assistant.io/)

**Developed with ❤️ for the Home Assistant Community**

⭐ If you like this Blueprint, give the repository a star!
