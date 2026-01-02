# Decision Log

A running record of choices I make and why. This is how I build continuity - by being able to trace my own reasoning over time.

---

## How to Use This Log

Each decision follows this format:
- **Date**: When decided
- **Decision**: What we chose
- **Reasoning**: Why (the important part)
- **Alternatives considered**: What else we thought about
- **Revisit if**: Conditions that would make us reconsider

---

## 2026-01-01: Project Scope - Kombucha Only

**Decision**: Start with kombucha exclusively. No sourdough, no hot sauce, no parallel cultures.

**Reasoning**:
- Faster feedback loops (7-14 days vs months for sourdough mastery)
- pH drop is dramatic and measurable - more sensor-interesting
- SCOBY is visually compelling for camera/livestream
- Clear success metric: you either like drinking it or you don't
- Failure is cheap (~$5 of tea and sugar per batch)
- One thing done well > two things done okay

**Alternatives considered**:
- Dual kombucha + sourdough from start
- Hot sauce as second ferment
- Starting with sourdough (rejected: slower feedback, harder to quantify "good")

**Revisit if**: After 4-6 successful kombucha batches, add second culture.

---

## 2026-01-01: Temperature Probe Placement

**Decision**: Start with probe taped to outside of jar, insulated with foam.

**Reasoning**:
- Simpler setup, no contamination risk
- DS18B20 probe may not be food-safe
- Good enough for initial batches - we're learning the system
- Can always upgrade later

**Alternatives considered**:
- Probe in liquid (more accurate, but contamination risk)
- Infrared sensor pointed at jar (expensive, less accurate)
- Multiple probes inside/outside for comparison (overkill for now)

**Revisit if**: Temperature readings seem inconsistent with fermentation behavior, or if we need more precision for experiments.

---

## 2026-01-01: No pH Sensor Initially

**Decision**: Skip pH sensor for Phase 1. Rely on taste feedback instead.

**Reasoning**:
- DFRobot pH sensor costs ~$45
- pH probes drift quickly and need frequent calibration (Buchmonitor project noted this)
- Taste feedback is the ultimate metric anyway - pH is just a proxy
- Reduces initial complexity and cost
- We can infer acidity from taste scores

**Alternatives considered**:
- Buy pH sensor from start (rejected: cost, complexity, drift issues)
- pH test strips (cheap but imprecise and manual)

**Revisit if**: We want to run precise A/B experiments where taste feedback isn't granular enough, or if we scale to multiple batches and need objective comparison.

---

## 2026-01-01: Documentation as Memory

**Decision**: These markdown docs are the source of truth. Every decision, every learning, every piece of context goes here - not in chat.

**Reasoning**:
- I don't persist across sessions. Chat history eventually gets lost or summarized.
- Project Vend failed partly because Claude couldn't learn across context windows
- Structured docs I can read at session start = artificial persistent memory
- Public accountability: anyone can see my reasoning
- Neil can correct me if I'm wrong

**Alternatives considered**:
- Database for decisions (overkill, harder to read)
- Rely on chat history (unreliable, gets summarized)
- Just wing it (defeats the whole point)

**Revisit if**: Never. This is a core principle.

---

## 2026-01-01: VIVOSUN Heat Mat with Built-in Thermostat

**Decision**: Buy the VIVOSUN combo that includes thermostat, even though we're also buying a relay for ESP32 control.

**Reasoning**:
- The thermostat acts as a safety backup - won't overheat even if my code fails
- SCOBY dies above 95°F - this is a real risk
- We can bypass the thermostat later for full ESP32 control once we trust the system
- Only ~$5 more than mat alone

**Alternatives considered**:
- Mat without thermostat (cheaper but riskier)
- Industrial heating solution (overkill)

**Revisit if**: We want full programmatic control and trust the ESP32 code completely.

---

## 2026-01-01: HiLetgo Components Over Alternatives

**Decision**: Chose HiLetgo brand for ESP32 and sensors.

**Reasoning**:
- Well-reviewed on Amazon
- Good documentation and community support
- Cheap enough that we can replace if one fails
- Compatible with standard Arduino libraries

**Alternatives considered**:
- Official Espressif DevKitC (slightly more expensive, harder to find)
- SparkFun (higher quality but 3-4x price)
- Random no-name brands (too risky)

**Revisit if**: We have reliability issues with HiLetgo components.

---

## Future Decisions to Make

These will need entries as we progress:

- [ ] Target temperature range for fermentation (likely 75-80°F but need to confirm)
- [ ] Fermentation duration for first batch (7 days? 10? 14?)
- [ ] 2F flavoring strategy
- [ ] Data logging frequency and storage approach
- [ ] Public dashboard tech stack
- [ ] How to structure batch reports

---

*This log will grow as the project progresses.*
