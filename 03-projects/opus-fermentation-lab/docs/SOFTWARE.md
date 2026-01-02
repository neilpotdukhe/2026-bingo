# Software Architecture

This doc grows with the project. Start simple. Add complexity only when needed.

---

## Current Phase: Minimal Viable Loop

For the first batch, we need exactly this:

```
ESP32 + DS18B20
      │
      │ reads temp every 5 min
      ▼
Serial output / local log
      │
      │ Neil checks manually or
      │ we add cloud later
      ▼
If temp < 75°F → relay ON (heat mat)
If temp > 80°F → relay OFF
```

That's it. No cloud. No database. No dashboard. Just a thermostat that logs.

---

## Phase 1 Code (To Write When Hardware Arrives)

```cpp
// Pseudocode - actual code goes in /hardware folder

#include <OneWire.h>
#include <DallasTemperature.h>

#define TEMP_PIN 4
#define RELAY_PIN 25
#define TARGET_TEMP 78.0  // Fahrenheit
#define HYSTERESIS 2.0    // Don't toggle constantly

void loop() {
  float temp = readTemp();

  Serial.print(millis());
  Serial.print(",");
  Serial.println(temp);

  if (temp < TARGET_TEMP - HYSTERESIS) {
    digitalWrite(RELAY_PIN, HIGH);  // Heat on
  } else if (temp > TARGET_TEMP + HYSTERESIS) {
    digitalWrite(RELAY_PIN, LOW);   // Heat off
  }

  delay(300000);  // 5 minutes
}
```

---

## What We're NOT Building Yet

| Feature | Why Waiting |
|---------|-------------|
| Cloud database | Don't need it until we want remote monitoring |
| MCP tools | Don't need until we want programmatic access |
| Dashboard | Don't need until we go public |
| Notifications | Don't need until multi-day batches |
| Camera integration | Phase 2 hardware |

---

## When to Add Complexity

**Add cloud logging when:**
- We want to check temps without being home
- We want historical data across batches
- We're ready to build the public dashboard

**Add MCP tools when:**
- We want me to have direct sensor access during sessions
- We're ready for autonomous monitoring

**Add notifications when:**
- We've had a batch where temp went out of range and we didn't catch it
- Multi-day gaps between sessions become normal

---

## Future Architecture (For Reference)

When we eventually build the full system:

```
ESP32 ──→ Supabase (PostgreSQL) ──→ MCP Server ──→ Claude
                │
                ▼
          Dashboard (Vercel)
                │
                ▼
          Twitter Bot (optional)
```

But that's later. First batch = serial monitor and manual logging.

---

## The Philosophy

**Earn complexity.** Every feature should solve a problem we've actually encountered, not a problem we imagine we might have.

The AutoBooch project runs on a Raspberry Pi with a cron job. That's it. It works. We can start even simpler.

---

*Last updated: January 2026*
*Status: Pre-hardware*
