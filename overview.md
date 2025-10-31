# World Simulation & Storytelling System

This document repository captures requirements for a layered RPG/fantasy world simulation and storytelling framework. It includes the following information:

1. **The System** – how the world state is conceptualized, managed, and progressed.  
2. **Tools** – how the state of the world system is communicated to players. 

---

## 1. The System

### Guiding Principles
- The project serves to **assist in telling rich and broad stories**.  
- It abstracts changes across the **whole world** while weaving **narrative structure**.  
- It is intended to be **woven together with stories acted out by human TTRPG players**.  
- Events and rolls always translate into **narrative beats** that enhance gameplay.  
- The system emphasizes **human play and entertainment** over pure simulation.  

### World Layers
1. [**Individuals**](/World%20Layers/Individuals/individuals.md)
   - Generalized, ttrpg system-agnostic stat blocks with attributes, abilities, motivations, resources.
   - Can spark **Champion Paths** through deeds.

2. [**Clans**](/World%20Layers/Clans/clans.md)
   - Families, guild cells, adventuring parties.
   - Traits inherited from individuals.

3. [**Communities**](/World%20Layers/Communities/communities.md)
   - Villages, towns, tribes.
   - Stats: Stability, Prosperity, Influence.
   - Track **Needs** (food, trade, protection, leadership, faith, health).

4. [**Realms**](/World%20Layers/Realms/realms.md)
   - Provinces, kingdoms, factions.
   - Stats: Power, Unity, Prestige.

5. [**World**](/World%20Layers/World/world.md)
   - Wars, plagues, migrations, pantheon rivalries.
   - Driven by arcs and cultural drift.

### Champion Emergence
- **Champion Seeds**: notable deeds can spark proto-champions.  
- **Growth by Deeds**:  
  - After **Victories**:  
    - Champions may gain stats, traits, or progress along a Champion Path.  
    - Example outcomes: a villager who slays a bandit becomes more skilled in arms; a diplomat who resolves a feud gains Influence.  
    - Represented with d20 rolls, often granting incremental growth or new abilities.  
  - After **Losses**:  
    - Champions may grow in spite of defeat, rejection, or tragedy.  
    - These moments produce traits tied to **resilience, bitterness, or reinvention**.  
    - Example outcomes:  
      - A scorned outcast hardens into a cunning survivor.  
      - A fallen warrior discovers spiritual or arcane strength after disgrace.  
      - A betrayed ally becomes a calculating villain or revolutionary.  
    - Mechanically: roll a d20 after a significant loss; on success, the champion gains a **Path Shift** (stat bonus, dark talent, or resilience trait). On failure, Fate increases and the loss scars them, but growth may still come later.  
  - This ensures both triumphs and tragedies can forge figures of influence.   
- **Rise and Fall**: Fame and Fate increase with deeds; high Fate introduces decline checks.  
- **Community Impact**: living champions grant bonuses; loss triggers unrest.

### Culture & Stories
- **Cultural Traits**: Valor vs. Caution, Collective vs. Individual, Tradition vs. Innovation, Honor vs. Pragmatism.  
- **Tokens → Hooks Structure**:
  - **Story Tokens**: mechanical markers produced by events (Triumph, Tragedy, Betrayal, Discovery).  
  - **Story Hooks**: narrative invitations created when tokens are revealed in play. Hooks show how tokens can engage the players or world.  
  - Example:  
    - Token = `tragedy:granary-burned`  
    - Hook = “Farmers consider raiding Rivergate’s storehouses. Do the players intervene?”  
- **Propagation**:
  - Tokens spread across communities via trade, rumor, or pantheon influence.  
  - Hooks emerge where player-facing opportunities arise.  

### Pantheon
- Gods embody **concepts and forces**, with hierarchy influenced by Greek, Roman, and Celtic traditions.  
- **High Triad**: Aureon (Sky), Neritha (Waters), Tharos (Stone).  
- **Middle Court**: Veyra (Fertility), Kaelen (War), Liora (Dreams).  
- **Wild Powers**: Fenros (Hunt), Morwen (Shadow), Cindral (Trickery).  
- Rivalries and mystery: possible missing or cast-out god.

### Community Needs
Tracked for each community:
- Food & Water  
- Protection & Security  
- Trade & Wealth  
- Leadership & Order  
- Faith & Culture  
- Health & Shelter  

Mechanics:
- Status values: Abundant, Stable, Limited, Strained, Failing, Divided, Contested.  
- Each World Turn: roll for strained needs (DC 12).  
- Failures → generate **Story Tokens**.  
- Tokens then become **Story Hooks** when presented to players or woven into narrative arcs.

### NPCs
- **Major NPCs**: champions, villains, leaders, gods.  
- **Supporting NPCs**: named, tracked if recurring.  
- **Background NPCs**: quick archetype, trait, motivation, stat die.  
- Generated based on community stats, pantheon influence, and unmet needs.  
- Can elevate into major NPCs through events or player interaction.

### Story Arcs
- **Tokens fuel arcs**: collected tokens accumulate and shape broader narratives.  
- Arcs at individual, community, or world scale follow narrative rhythm:
  - Call to Change  
  - Rising Action  
  - Climax  
  - Resolution  
- Hooks ensure players see and engage with arcs as they unfold.  

---

## 2. Tools

### Recording & Storage
- **Markdown files** as the source of truth.  
- Structure:
  - `/genesis` — origin cycle, pantheon.  
  - `/cultures` — cultural traits and stats.  
  - `/heroes` — individual sheets.  
  - `/communities` — community sheets with needs, NPCs, tokens.  
  - `/worldstate` — chronicle of turns.  
- Each World Turn = snapshot file (`turn-###.md`).  
- Only changed entities updated; cross-links for context.  
- Versioning with Git.

### Visualization
- **Web app world map**:
  - Zoomable map with timeline slider.  
  - Communities shown as deity-colored markers.  
  - Detail panels: needs, tokens, hooks, champions, culture.  
  - Filters: unmet needs, patron gods.  
  - Optional layers: heatmaps, pantheon influence, arc icons.

### AI Agents (Writers Room)
Roles to assist in world/story progression:
- **Showrunner** — coordination.  
- **Pitch Writer** — plot seeds.  
- **Beat Weaver** — story outlines.  
- **Lore Canonist** — continuity checks.  
- **Systems Editor** — mechanics.  
- **Simulator** — rolls and outcomes.  
- **Memetic Analyst** — story spread and cultural drift.  
- **Sensitivity Reader** — cultural safety.  
- **Diff Builder** — markdown/JSON updates.  

Pipeline: pitches → beats → checks → rolls → tokens → hooks → updates → human approval.

### System Translators
Tools that convert world state into popular TTRPG formats so players can interact with the system directly in their preferred ruleset:
- **D&D 5e**:  
  - Convert individuals into NPC/monster stat blocks.  
  - Map communities into settlement stat sheets (prosperity, defense, morale).  
  - Translate Story Hooks into quest prompts and downtime events.  
- **Pathfinder 2e**:  
  - Champion Paths translated into Archetypes or Class Progressions.  
  - Communities expressed with settlement rules.  
- **Powered by the Apocalypse (PbtA)**:  
  - Tokens → Fronts and Clocks.  
  - Hooks → GM Moves or narrative prompts.  
- **Generic**:  
  - Export into JSON schema that can be adapted for any ruleset.  
  - Maintain alignment between simulation state and narrative play aids.
