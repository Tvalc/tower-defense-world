# Level Design Specification

## Description
Individual level layouts, progression, and mechanics

## Content
```markdown
# Level Design Document: Snib Tower Defense Extravaganza Celebration

## 1. INTRODUCTION

This document defines the structure, pacing, progression, layout, and environmental storytelling for the 100 levels (each with 10 stages) of Snib Tower Defense Extravaganza Celebration. Designs are optimized for web performance, mobile/desktop play, and support both touch and mouse controls.

---

## 2. LEVEL STRUCTURE & PROGRESSION

### 2.1. LEVEL & STAGE ORGANIZATION

- **Levels:** 100, each with a unique, humorous sci-fi or fantasy theme.
- **Stages per Level:** 10, escalating in complexity and difficulty.
- **Waves per Stage:** 10 standard waves + 1 boss wave.
- **Enemy Progression:** Each level introduces a new enemy type; waves draw randomly from all previously unlocked enemies.
- **Objective:** Prevent enemies from reaching the end of their path(s). Each escaped enemy decrements player HP by 1.
- **Completion:** Stage is complete when all waves (including boss) are defeated. Level is complete after all 10 stages.
- **Persistence:** Towers, upgrades, and base-building features persist and unlock new options between levels.

### 2.2. DIFFICULTY CURVE & PACING

- **Early Levels (1-10):** Simple paths, few branches, slow enemies, basic tower placement, introduce core mechanics gradually.
- **Mid Levels (11-60):** Multiple paths, environmental hazards, increased enemy speed/hp/abilities, unlock advanced towers and spells.
- **Late Levels (61-100):** Complex, multi-lane maps, enemy resistances, flying/swarm/boss mechanics, require advanced base-building strategies.

### 2.3. ENVIRONMENTAL STORYTELLING

- **Level Themes:** Each level’s visual design and name reflect its sci-fi/fantasy humor (e.g., “Quantum Goblin Labs”, “Cyborg Dragon’s Lair”, “The Intergalactic Sock Drawer”).
- **Map Layout:** Environmental elements (e.g., crashed UFOs, magical forests, robots-on-strike signs) tell the story visually.
- **Stage Titles:** Each stage has a sub-theme (e.g., “Sockpocalypse”, “Goblin Coffee Break”), adding flavor and variety.

---

## 3. MAP LAYOUTS & INTERACTIVE ELEMENTS

### 3.1. MAP CONSTRAINTS

- **Performance:** Max 2-3 paths per map, 20-30 total interactive assets per stage.
- **Responsive Design:** All maps scale to fit phones, tablets, desktops. UI overlays adapt to orientation/size.
- **Asset Streaming:** Large assets (backgrounds, boss sprites) load asynchronously; reuse tile sets and path elements for fast load.

### 3.2. PATH DESIGN

- **Path Shape Variety:** S-curves, figure 8s, branching, loops, and converging paths introduced as difficulty increases.
- **Placement Zones:** Highlighted tiles or regions near paths for legal tower placement (never on paths). Touch-friendly hitboxes.
- **Obstacles:** Some maps contain destructible/indestructible obstacles (rocks, magical barriers) blocking tower placements.

### 3.3. PLAYER INTERACTIVES

- **Towers:** Placed near paths; types include Basic, Slow, AoE, DoT, anti-air, summoners, heroes, vehicles.
- **Spells:** Drag-and-drop or tap-to-cast area spells; cooldowns and resource costs.
- **Base Building:** Between levels, players spend Snib Glitter to unlock/upgrade persistent features and towers.
- **Collectables:** Snib Glitter explodes from defeated enemies and must be tapped/clicked to collect (auto-collect after delay).

---

## 4. LEVEL FLOW & PLAYER GUIDANCE

### 4.1. ONBOARDING & TUTORIALS

- **Level 1:** Interactive tutorial (touch/click indicators, tooltips) for tower placement, upgrades, spell usage, Snib Glitter collection.
- **First 5 Levels:** Gradual unlock of towers and features; pop-up guidance for new enemy/tower types.

### 4.2. UI & HUD

- **Always Visible:** Player HP, current stage/level, wave number, Snib Glitter, tower menu button.
- **Placement Mode:** Ghosted tower previews, valid/invalid placement highlights, cancel button.
- **Menus:** 
  - **Main Menu:** Start, Continue, Base Building, Tower Encyclopedia, Settings.
  - **Pause Menu:** Resume, Audio, Controls, Restart Stage, Exit.
  - **Stage Summary:** Stats, earned Snib Glitter, new unlocks, funny recap.

---

## 5. PERFORMANCE & TECHNICAL CONSIDERATIONS

- **HTML5/JavaScript, Pixi.js or Phaser recommended for rendering.**
- **Prefab maps & tilemaps for fast load.**
- **Spritesheets for enemies/towers; limit unique asset count per stage.**
- **UI drawn with scalable vector assets where possible.**
- **Touch/mouse input abstraction for cross-platform compatibility.**
- **Level & enemy data loaded as lightweight JSON.**

---

## 6. LEVEL & STAGE THEMES (EXAMPLES)

**Level 1: Quantum Goblin Labs**
  - Stage 1: “Lab Coat Mayhem”
  - Stage 2: “Proton Punchbreak”
  - ...
  - Stage 10: “Experiment Gone Bananas!”

**Level 2: The Intergalactic Sock Drawer**
  - Stage 1: “Sockpocalypse Now”
  - Stage 2: “Lint Trap Trouble”
  - ...
  - Stage 10: “Lord of the Socks”

*(Continue through Level 100 with unique, funny themes and sub-stages; see Appendix for naming conventions and full list.)*

---

## 7. DIFFICULTY & ENEMY DISTRIBUTION

- **Enemy Types:** 1 new enemy per level, ramping up to 100 unique types by Level 100 (see Enemy Distribution Table in GDD).
- **Wave Construction:** Each wave randomly selects from all unlocked enemies, weighted toward newer/stronger types in higher stages.
- **Bosses:** Each stage ends with a unique or upscaled boss variant (e.g., “Mega Quantum Goblin”).

---

## 8. SCORING & REWARD SYSTEM

- **Snib Glitter:** Each enemy drops coins (auto/active collect); harder enemies drop more (see Snib Glitter Value Table).
- **Stage Completion:** Additional Snib Glitter bonus for no leaks, fast clears, perfect tower placement.
- **Unlocks:** Persistent upgrades, new towers, spells, and cosmetic map elements unlocked between levels.

---

## 9. EXAMPLE MAP LAYOUTS

### 9.1. Mobile (Vertical) Example

- **Path:** Winding S-curve occupying center 60% of screen.
- **Placement Zones:** 2 columns on each side, 3-5 tiles deep.
- **Obstacles:** 1-2 rocks near high-value placement spots.

### 9.2. Desktop (Horizontal) Example

- **Path:** Double-loop with a branch, covers lower 70% of screen width.
- **Placement Zones:** Wedges in corners and along loops, plus a central “power spot.”
- **Obstacles:** Environmental hazards (e.g., electrified puddles).

---

## 10. APPENDIX: LEVEL & STAGE NAMING CONVENTIONS

- **Levels:** Alternately sci-fi and fantasy, always humorous (avoid repeats).
- **Stages:** Each is a pun/wordplay on the level theme.
- **Examples:** “Unicorn Traffic Jam”, “Caffeinated Necromancer’s Basement”, “The Lazer Lizard Lagoon”.

---

## 11. IMPLEMENTATION CHECKLIST

- [ ] Each level has a unique name/theme and 10 sub-stages.
- [ ] Map layouts designed for both mobile and desktop ratios.
- [ ] Towers and spells introduced progressively.
- [ ] Enemy types distributed as per GDD.
- [ ] All asset counts and load times optimized.
- [ ] UI/UX is responsive and touch/mouse compatible.
- [ ] Environmental storytelling through map art and interactive elements.

---

## 12. OPEN DESIGN QUESTIONS

- **Tower and enemy specifics:** See GDD; to be finalized in collaboration with art and engineering.
- **Stage and level naming master list:** To be generated with procedural tools or curated for humor/variety.

---

*This Level Design Document is consistent with the Snib Tower Defense Extravaganza Celebration Game Design Document, referencing all major mechanics and ensuring actionable, performant, and fun browser-based gameplay.*

```
If you need the full 100-level/1000-stage naming masterlist, or detailed enemy/tower design tables, request them as follow-ups for focused implementation.


---
*Generated on 7/17/2025*
