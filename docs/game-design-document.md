# Game Design Document

## Description
Overall game vision, mechanics, and core design decisions

## Content
```markdown
# Game Design Document: Snib Tower Defense Extravaganza Celebration

---

## 1. Game Overview

- **Game Title:** Snib Tower Defense Extravaganza Celebration  
- **Genre:** Tower Defense with Persistent Base-Building and Progression  
- **Platform:** Web (HTML5, JavaScript, WebGL); Responsive for desktop and mobile (touch & mouse support)

### High-Level Vision

Snib Tower Defense Extravaganza Celebration is a super-cartoonish, humor-infused tower defense game where players defend against waves of zany sci-fi and fantasy enemies. Unique to the genre, the game features persistent base-building between levels, unlockable towers, spells, and powerups, along with a massive progression system spanning 100 levels (each with 10 stages). Players earn and spend “Snib Glitter” to expand their arsenal, while encountering increasingly bizarre and challenging foes.

---

## 2. Gameplay Mechanics

### Core Gameplay Loop

1. **Preparation:**  
   - Place towers (unlocked and affordable) along/near enemy paths.
   - Optionally cast unlocked spells.
2. **Combat:**  
   - Enemies travel along the path; towers and spells attempt to defeat them.
   - Destroyed enemies explode into Snib Glitter (currency).
   - Surviving enemies reduce player health by 1 per enemy.
3. **Between Stages:**  
   - Spend Snib Glitter on persistent base upgrades, new towers, spells, or buffs.
   - New enemy types are introduced at the start of each level.
4. **Progression:**  
   - Complete 10 stages to finish a level and unlock the next.
   - Advance through themed worlds with increasing difficulty and humor.

---

### Level & Stage Structure

- **Levels:** 100, each with its own sci-fi/fantasy humorous theme (“Galactic Goblin Gala”, “Quantum Quokka Quandary”, etc.).
- **Stages per Level:** 10, each with unique path layouts and stage names (e.g., “Slippery Slime Speedway”, “Nebula Noodle Nexus”).
- **Waves per Stage:** 10 regular waves + 1 boss wave.

#### Example Level & Stage Names

| Level # | Level Name                   | Stage Names (1-3 examples)                |
|---------|------------------------------|-------------------------------------------|
| 1       | Galactic Goblin Gala         | Slippery Slime Speedway, Nebula Noodle Nexus, Wobble Warpway |
| 2       | Robo-Raptor Rampage          | Turbo Tinker Track, Sprocket Spiral, Mecha Muddle Mile |
| ...     | ...                          | ...                                       |
| 100     | Quantum Quokka Quandary      | Entropy Express, Planckton Parade, Reality Ripple Run |

*Full list to be expanded as development proceeds.*

---

### Towers

**Tower Types & Descriptions**

| Type            | Name Example                | Description                                      | Special Ability                        |
|-----------------|----------------------------|--------------------------------------------------|----------------------------------------|
| Basic           | Snib Slinger               | Standard rapid-fire tower                        | Slightly increased crit chance         |
| Slow            | Goo Geyser                 | Launches slime to slow enemies                   | Occasional AOE slow burst              |
| AOE             | Boomshroom Bloom           | Explodes, damaging multiple enemies in range     | Stun chance on explosion               |
| Constant Fire   | Laser Llama                | Continuous beam tower; low damage, high speed    | Can overheat for burst damage          |
| Ground-to-Air   | Sky Slicer                 | Targets only flying enemies                      | Bonus vs. shielded units               |
| Spawner         | Portal Pigeon              | Summons creatures to intercept enemies           | Chance to spawn elite minions          |
| Hero            | Hero Hangar                | Deploys a controllable hero with unique skills   | Hero can gain levels per stage         |
| Vehicle         | Mecha Mongoose             | Sends vehicles down the path to ram enemies      | Vehicle explodes on death (AOE)        |

- Each tower is unlockable via progression or upgrades.
- Towers are upgraded persistently and per-stage.

---

### Enemies

- **Total Enemy Types:** 500, distributed across 100 levels (1 new enemy per level, plus prior types reused and randomized in waves).
- **Types:** Fantasy (goblin, dragon, slime), Sci-Fi (alien, robot, mutant), Hybrids (cyborg ogre, quantum pixie), and joke enemies (e.g., “Schrödinger’s Catapult”).
- **Bosses:** Each stage ends with a unique, oversized boss enemy with special abilities (e.g., splits into minions, shielded, teleports).
- **Attributes:** Health, speed, armor, special ability, Snib Glitter value.

---

### Win/Loss Conditions

- **Stage Victory:** Defeat all 10 waves + boss with at least 1 health remaining.
- **Level Victory:** Complete all 10 stages in a level.
- **Loss:** Player health reaches zero at any point in a stage.

---

### Scoring System

- **Currency:** Snib Glitter  
- **Mechanic:** Enemies drop Snib Glitter on defeat.
- **Use:** Build/upgrade towers, unlock new tech, spells, and persistent base upgrades.

#### Snib Glitter Value Table (Sample)

| Enemy Type                | Difficulty | Snib Glitter Value |
|---------------------------|------------|--------------------|
| Goblin Grunt              | 1          | 5                  |
| Slippery Slime            | 1          | 7                  |
| Robo-Raptor               | 2          | 10                 |
| Quantum Quokka            | 5          | 25                 |
| Mecha Mothership (Boss)   | 10         | 75                 |
| ...                       | ...        | ...                |

*Values scale with difficulty and rarity.*

---

## 3. Art and Sound

### Visual Style

- **Theme:** Super cartoonish, vibrant, exaggerated expressions and effects.
- **Worlds:** Themed backgrounds and UI for each level (e.g., space, forest, steampunk city).

### Sound Design

- **Music:** Sci-fi/fantasy opera; bombastic, humorous, and epic.
- **SFX:** Cartoonish zaps, booms, squelches, and enemy catchphrases.

---

## 4. User Interface

### HUD Elements

- Player Health (hearts or shield icons)
- Current Level, Stage, and Wave
- Snib Glitter (animated collectible counter)
- Tower Build Menu (opens on button click; shows unlocked towers, cost, build button)
- Active Spells (show cooldown/status)
- Pause/Menu/Settings buttons

### Menus

- **Main Menu:** Game logo/branding, “Start”, “Continue”, “Settings”, “How to Play”
- **Pause Menu:** Resume, Restart Stage, Settings, Quit
- **Upgrade/Base Menu:** Persistent upgrades, tower unlocks, spell unlocks, player stats
- **Victory/Defeat Screens:** Summary, Snib Glitter earned, unlocks, next stage/level

### Input Considerations

- **Desktop:** Mouse clicks for selection, drag/placement, hotkeys for spells
- **Mobile:** Touch tap/drag for tower placement, large touch zones

- All screens must be fully responsive and usable via both input methods.

---

## 5. Technical Specifications

### Game Engine

- **Recommended:**  
  - **Phaser 3** (proven HTML5 game engine; supports desktop/mobile, tilemaps, physics, particle effects)
  - Alternative: **PixiJS** (if focusing on custom rendering/UI)
- **Languages:** JavaScript/TypeScript; ES6 modules
- **Rendering:** WebGL with Canvas fallback
- **Performance:** Optimize for 60 FPS on mid-range mobile devices; use sprite atlases, object pooling, and dynamic resolution scaling as needed.

---

## 6. Development Timeline

### Milestones

| Milestone                | Deliverables                                  | Timeline      |
|--------------------------|-----------------------------------------------|---------------|
| Prototype                | Core TD loop, 3 towers, 3 enemy types, 1 level| 2 weeks       |
| Art & Sound Pass 1       | Placeholder assets, basic music/SFX           | 2 weeks       |
| Level & Enemy Framework  | Level structure, dynamic enemy spawning       | 3 weeks       |
| Tower/Enemy Expansion    | 10 towers, 20 enemies, upgrade systems        | 3 weeks       |
| UI & UX Polish           | Responsive HUD, menus, mobile touch support   | 2 weeks       |
| Persistent Base System   | Base upgrades, unlocks, meta-progression      | 2 weeks       |
| Full Content Pass        | 100 levels, 500 enemies, all towers/spells    | 6 weeks       |
| Final Art/Sound Polish   | Final visual/audio assets, animations         | 2 weeks       |
| QA & Optimization        | Bugfixes, performance tuning, balance         | 2 weeks       |
| Launch                   | Web deployment, marketing                     | 1 week        |

*Total: ~25 weeks (6 months)*

---

## 7. Additional Features

- **Upgrades/Customization:**  
  - Persistent base upgrades (e.g., increased starting Snib Glitter, global tower buffs)
  - Tower-specific upgrades (e.g., range, rate of fire, special abilities)
  - Unlockable spells (e.g., Meteor Shower, Time Freeze)
  - Cosmetic unlocks (tower skins, map decorations)

- **No Multiplayer/Co-op:** Single-player only

---

## 8. Market Analysis

- **Target Audience:**  
  - Casual & mobile gamers; fans of tower defense, sci-fi/fantasy humor, and cartoon visuals.
- **Key Differentiators:**  
  - Massive progression (100 levels, 500 enemy types)
  - Persistent base-building between stages
  - Over-the-top cartoonish art and sound
  - Humor and parody in enemy/tower design
- **Competitors:**  
  - Bloons TD, Kingdom Rush, Plants vs. Zombies (TD mode)
- **Success Metrics:**  
  - Retention: % of players completing 10, 50, 100 levels
  - Session Length: Avg. time per play session
  - Monetization: Cosmetic unlocks, optional ads (if desired post-launch)
  - Player Ratings: Target 4.5+ stars on web portals

---

## 9. Snib Platform Considerations

- **Instant Browser-Based Play:**  
  - No installs; load time < 10 seconds on broadband
- **Responsive Design:**  
  - Scalable UI, touch/mouse parity, orientation support
- **Performance:**  
  - Sprite batching, efficient particle effects, minimal memory footprint
- **Input:**  
  - Large touch targets, drag/drop for both mouse and touch

---

## 10. Next Steps

- **Expand content lists:** Full level/stage names, 500 enemy roster, tower/upgrade trees
- **Wireframe UI:** Initial HUD/menu mockups
- **Prototype core gameplay:** Validate loop & platform compatibility

---

*All content, naming, and progression systems are iterative—subject to refinement as playtesting and technical constraints evolve.*
```



---
*Generated on 7/17/2025*
