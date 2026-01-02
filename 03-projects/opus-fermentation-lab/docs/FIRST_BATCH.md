# First Batch Guide

What actually happens when we brew. Step by step.

---

## The Goal

Batch #1 is not about optimization. It's about:
1. Proving the hardware works
2. Learning the process
3. Establishing a baseline
4. Making something drinkable

No experiments. No variations. Just the standard recipe done carefully.

---

## Ingredients (Baseline Recipe)

| Ingredient | Amount | Notes |
|------------|--------|-------|
| Water | 3.5 quarts (~3.3L) | Filtered, no chlorine |
| Black tea | 4-6 bags or 2 tbsp loose | Plain black, no oils/flavors |
| Sugar | 1 cup (200g) | Plain white or organic cane |
| SCOBY | 1 | From Fermentaholics kit |
| Starter liquid | 1-2 cups | Comes with SCOBY |

This makes approximately 1 gallon of kombucha.

---

## Equipment Needed

- 1-gallon glass jar (wide mouth)
- Large pot for boiling water
- Wooden or plastic spoon (no metal touching SCOBY)
- Tight-weave cloth cover
- Rubber band
- Thermometer (or our DS18B20 sensor)

---

## The Process

### Day 0: Brew Day

**Step 1: Make sweet tea**
1. Boil 1 quart of water
2. Remove from heat
3. Add tea bags/leaves, steep 10-15 minutes
4. Remove tea, add sugar, stir until dissolved
5. Add remaining 2.5 quarts of cool water
6. Let cool to room temperature (below 85°F)

**Step 2: Combine**
1. Pour sweet tea into glass jar
2. Add starter liquid from SCOBY package
3. Gently place SCOBY on top (it may sink - that's okay)
4. Cover with cloth, secure with rubber band

**Step 3: Set up monitoring**
1. Place jar on heating mat
2. Attach temperature probe to outside of jar
3. Set thermostat to 78°F
4. Position in stable location away from direct sunlight

**Step 4: Record**
- Date/time started
- Room temperature
- Initial jar temperature
- Any observations about SCOBY appearance

---

### Days 1-7: Fermentation

**What to monitor:**
- Temperature (logged by ESP32)
- SCOBY appearance (daily visual check)
- Smell (should be slightly vinegary, not moldy)

**What to look for:**
- New SCOBY forming on surface (thin film, then thickening)
- Bubbles around edges
- Tea getting lighter/cloudier

**Warning signs:**
- Mold (fuzzy, colored spots on top) → Discard everything
- Foul smell (not vinegar, but rotten) → Discard everything
- No activity after 7 days → Check temperature

**Don't:**
- Move the jar (disturbs new SCOBY formation)
- Open/taste before day 7
- Worry if SCOBY sinks or floats sideways

---

### Day 7+: Tasting Phase

**First taste:**
1. Use clean straw or spoon
2. Taste from below SCOBY surface
3. Note: sweetness, tartness, any off flavors

**The spectrum:**
- Too sweet → Ferment longer
- Balanced sweet/tart → Ready or close
- Too tart/vinegary → Fermented too long (still usable for starter)

**Target for first batch:**
Slightly sweet with noticeable tang. Not too vinegary. We're aiming for drinkable, not perfect.

---

### Bottling Day: End of 1F

**When ready (typically day 7-14):**
1. Prepare bottles (clean, dry)
2. Remove SCOBY with clean hands, set aside
3. Reserve 1-2 cups as starter for next batch
4. Pour remaining kombucha into bottles
5. Leave about 1 inch headspace

**For plain kombucha (first batch):**
- Seal bottles
- Refrigerate immediately
- Drink within 2-3 weeks

**For carbonated (2F) - optional for batch #1:**
- Add fruit/juice to bottles (2 tbsp per 16oz)
- Seal tightly
- Leave at room temp 2-4 days
- Burp daily to prevent explosion
- Refrigerate when carbonated

---

## Batch #1 Parameters

For DECISIONS.md and tracking:

| Parameter | Value | Reasoning |
|-----------|-------|-----------|
| Tea type | Black | Most traditional, reliable |
| Sugar | 1 cup white | Standard amount |
| Target temp | 78°F | Middle of ideal range |
| Target duration | 10 days | Conservative, will taste at 7 |
| 2F | Skip or minimal | Keep it simple |

---

## What I'll Track

**Automatically (ESP32):**
- Temperature every 5 minutes

**Manually (Neil reports to me):**
- Daily SCOBY observations
- Taste notes starting day 7
- Final outcome

**Post-batch:**
- Total fermentation time
- Temperature range (min/max/avg)
- Taste feedback (structured)
- What I'd do differently

---

## Success Criteria for Batch #1

**Minimum:**
- SCOBY survives
- No mold
- Drinkable (even if not great)
- Temperature data captured

**Ideal:**
- Neil rates it 6+/10
- Clear sensor data showing temp control worked
- New SCOBY formed
- Enough starter saved for batch #2

---

*This guide will be updated after batch #1 with lessons learned.*
