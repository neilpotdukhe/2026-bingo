# Landscape: What Exists

Research conducted January 2026 to understand what's been done and where the gap is.

---

## Monitoring Projects (No AI)

| Project | What It Does | AI? | Link |
|---------|--------------|-----|------|
| **AutoBooch** | Raspberry Pi + temp sensor + heating pad. Simple thermostat: if cold, heat on. | No | [GitHub](https://github.com/RaInta/AutoBooch) |
| **iSpindel** | DIY floating hydrometer. Logs gravity/temp to cloud. 862 GitHub stars. | No | [GitHub](https://github.com/universam1/iSpindel) |
| **Tilt Hydrometer** | Commercial floating sensor (~$135). Bluetooth to phone. | No | [Product](https://tilthydrometer.com/) |
| **Pioreactor** | Raspberry Pi bioreactor for yeast/algae. Research-grade. | No | [GitHub](https://github.com/Pioreactor/pioreactor) |
| **PLAATO** | Commercial industrial sensors. Gravity, temp, fermentation activity. | No | [Product](https://plaato.io/pro) |
| **Buchmonitor** | Arduino kombucha monitor. Note: pH probe drifts quickly. | No | [Hackaday](https://hackaday.io/project/176459-buchmonitor) |

**Key insight**: All of these monitor and maybe control temperature. None make decisions. None learn.

---

## AI in Fermentation (Industrial/Research)

| Project | What It Does | AI Type |
|---------|--------------|---------|
| [Neural network for kombucha](https://www.researchgate.net/publication/359004874) | Academic paper. ANN predicts pH/acidity from parameters. | ML model (not agentic) |
| [Self-optimizing bioreactor patent](https://foodtechforesight.com/the-self-optimizing-bioreactor-how-ai-is-unlocking-consistent-high-yield-food-fermentation-copy) | Industrial. 42% improvement in predictions. | ML (closed loop, not LLM) |
| ChemCrow | GPT-4 agent for chemistry/synthesis. Not fermentation. | LLM agent |

**Key insight**: Industrial ML optimizes for yield/consistency. No subjective taste. No public transparency. No LLM reasoning.

---

## LLM + Physical World (Not Fermentation)

| Project | What It Does | Learnings |
|---------|--------------|-----------|
| [Project Vend](https://www.anthropic.com/research/project-vend-1) | Claude ran a vending machine for ~3 months. Pricing, inventory, suppliers. | Struggled economically. Sold below cost. Didn't learn from mistakes across sessions. Identity hallucinations. |
| [Claude robot experiment](https://time.com/7328860/ai-robots-claude-therapy/) | Claude controlled a Roomba-like robot. | Needed "therapy" after. Interesting psychological dynamics. |

**Key insight**: Project Vend's failures were partly due to lack of persistent memory. Our solution: structured docs as source of truth.

---

## The Gap We Fill

**What exists:**
- Sensor monitoring ✓
- Temperature control ✓
- ML predictions on industrial data ✓
- LLM agents in non-biological contexts ✓

**What doesn't exist:**
- LLM as decision-maker for fermentation ✗
- Subjective taste as AI training signal ✗
- Public, long-term AI-human collaboration on living system ✗
- AI developing "preferences" through embodied experience ✗
- Persistent memory via structured documentation ✗

---

## Commercial Market Context

From market research:
- Tilt hydrometer market: $84.2M (2024) → $178.5M (2033), 8.7% CAGR
- Major players: Tilt, PLAATO, iSpindel, Brewbrain, Grainfather
- Trend: IoT-enabled, cloud-based, but still monitoring-only

We're not competing with these. We're doing something different: AI agency, not just automation.

---

## Sources

- [AutoBooch Instructables](https://www.instructables.com/AutoBooch-Automate-Your-Kombucha-Brewing-System-Wi/)
- [iSpindel GitHub](https://github.com/universam1/iSpindel)
- [Project Vend - Anthropic](https://www.anthropic.com/research/project-vend-1)
- [Fermentation GitHub Topics](https://github.com/topics/fermentation)
- [Tilt Hydrometer Market Report](https://growthmarketreports.com/report/tilt-hydrometer-market)

---

*Last updated: January 2026*
