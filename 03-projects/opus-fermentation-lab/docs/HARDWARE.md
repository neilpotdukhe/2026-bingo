# Hardware Guide

Streamlined for **kombucha only**. Exact Amazon links included.

---

## Day 1 Order (~$110)

Order these now. Everything needed to start the first batch with sensor monitoring.

| Item | Link | Price |
|------|------|-------|
| ESP32 DevKit | [HiLetgo ESP-WROOM-32](https://www.amazon.com/HiLetgo-ESP-WROOM-32-Development-Microcontroller-Integrated/dp/B0718T232Z) | ~$10 |
| DS18B20 Temp Probes (5-pack) | [HiLetgo Waterproof 1M](https://www.amazon.com/HiLetgo-DS18B20-Temperature-Stainless-Waterproof/dp/B00M1PM55K) | ~$11 |
| 4-Channel Relay | [DIYables Relay Module](https://www.amazon.com/DIYables-4-Channel-Arduino-ESP8266-Raspberry/dp/B0BXKKYH5C) | ~$9 |
| Heat Mat + Thermostat | [VIVOSUN 10x20" Combo](https://www.amazon.com/VIVOSUN-Seedling-Digital-Thermostat-Standard/dp/B016MKY7C8) | ~$30 |
| Jumper Wires + Breadboard | [DIYables Kit](https://www.amazon.com/DIYables-Breadboard-Arduino-ESP8266-Raspberry/dp/B0CWZJ5V2C) | ~$12 |
| 1-Gallon Glass Jar | [kitchentoolz Wide Mouth](https://www.amazon.com/Pack-Kombucha-Fermenting-Cheesecloth-Kitchentoolz/dp/B0778SW4MC) | ~$20 |
| Organic SCOBY + Starter | [Fermentaholics USDA Organic](https://www.amazon.com/Fermentaholics-Kombucha-Twelve-Starter-Culture/dp/B01N7S1CV5) | ~$18 |

**Total: ~$110**

---

## Phase 2 (~$60)

Add after basic temp control loop is working.

| Item | Link | Price |
|------|------|-------|
| ESP32-CAM (2-pack w/ USB) | [HiLetgo ESP32-CAM](https://www.amazon.com/HiLetgo-ESP32-CAM-Development-Bluetooth-Raspberry/dp/B07RXPHYNM) | ~$16 |
| Swing Top Bottles (12-pack) | [Amber 16oz](https://www.amazon.com/Flip-Top-Kombucha-Airtight-Bottles-Fermentation/dp/B0891J95G1) | ~$28 |
| DHT22 Humidity Sensor | [HiLetgo DHT22](https://www.amazon.com/HiLetgo-Temperature-Humidity-Electronic-Practice/dp/B07D7W3TNX) | ~$10 |
| USB Power Supplies (2x) | Search "5V 3A USB-C" | ~$15 |

---

## Optional Upgrades

| Item | Why | Price |
|------|-----|-------|
| pH Sensor (DFRobot) | Direct acidity measurement | ~$45 |
| HX711 + Load Cell | Weigh for precision | ~$12 |
| Project enclosure | Clean wiring | ~$10 |

---

## Wiring (Kombucha Only)

```
                    ESP32 DevKit
                   ┌────────────┐
                   │            │
    DS18B20 ───────┤ GPIO 4     │  (1-Wire, use 4.7k pull-up resistor)
                   │            │
    Relay IN1 ─────┤ GPIO 25    │  (Heating mat control)
                   │            │
                   │      3V3 ──┼──→ DS18B20 VCC (red wire)
                   │      GND ──┼──→ Common ground
                   │       5V ──┼──→ Relay VCC
                   └────────────┘

DS18B20 Wiring:
  - Red → 3.3V
  - Black → GND
  - Yellow → GPIO 4 (with 4.7kΩ resistor between Yellow and Red)
```

---

## Physical Setup

```
┌─────────────────────────────────────────────────────────────────┐
│                     FERMENTATION STATION                         │
│                                                                  │
│      ┌──────────────────┐                                       │
│      │    KOMBUCHA      │                                       │
│      │      JAR         │                                       │
│      │                  │                                       │
│      │   ┌─DS18B20──┐   │  ← Probe taped to outside of jar     │
│      │   │ (probe)  │   │    (or in liquid if food-safe)       │
│      └───┴──────────┴───┘                                       │
│               │                                                  │
│      ═════════╧═════════                                        │
│          HEATING MAT                                             │
│       (relay controlled)                                         │
│      ═══════════════════                                        │
│                                                                  │
│      [ESP32]──────────── Nearby, connected via jumper wires     │
│      [Relay]──────────── Between ESP32 and heating mat power    │
└─────────────────────────────────────────────────────────────────┘
```

**Probe placement options:**
1. **Outside jar** - Tape probe to glass, insulate with foam. Less accurate but no contamination risk.
2. **In liquid** - Thread through cloth cover. More accurate but must be food-safe.

We'll start with option 1 (outside) for simplicity.

---

## Assembly Steps

### Step 1: Test ESP32
1. Install Arduino IDE + ESP32 board support
2. Upload blink sketch to verify board works
3. Connect to WiFi, verify with serial monitor

### Step 2: Test Temperature Sensor
1. Wire DS18B20 to GPIO 4 with 4.7kΩ pull-up
2. Upload OneWire + DallasTemperature example
3. Verify readings in serial monitor

### Step 3: Test Relay
1. Wire relay IN1 to GPIO 25
2. Test with LED before connecting heating mat
3. Verify HIGH/LOW toggles relay

### Step 4: Integration
1. Connect heating mat through relay
2. Write simple thermostat logic (target: 75-80°F)
3. Test full loop: temp drops → mat on → temp rises → mat off

### Step 5: Start Brewing
1. Make sweet tea (recipe in RECIPES.md when created)
2. Add SCOBY + starter liquid
3. Cover, place on mat, start logging

---

## Safety Notes

- **Relay isolation**: The DIYables relay is opto-isolated - good.
- **Water + electronics**: Keep ESP32 away from jar. Spills happen.
- **Heating mat**: Never exceed 85°F for kombucha. SCOBY dies above 95°F.
- **Power**: Use quality USB power supply. Cheap ones cause sensor noise.

---

## What We're NOT Buying Yet

| Item | Why Waiting |
|------|-------------|
| pH sensor | Expensive, probe drift issues. Taste is sufficient initially. |
| Load cell | Only needed for sourdough weighing. |
| Multiple temp probes | One jar = one probe. |
| Fancy enclosure | Get it working first. |

---

*Last updated: January 2026*
