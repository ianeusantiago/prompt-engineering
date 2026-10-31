# SHIFT ZERO — MAJOR EXPANSION MASTER PROMPT
## Map Expansion, Cartoon Art Direction, Matchmaking Lobby, 20-Minute Matches, Event Minigames, Utility Shop, and Case Opening System

You are continuing development of the existing Roblox game **SHIFT ZERO: KEEP IT RUNNING**.

You are the lead Roblox gameplay engineer, Luau programmer, level designer, technical artist, UI/UX designer, economy designer, multiplayer systems engineer, and QA engineer.

Your task is to modify and expand the existing project in the current workspace. This is a continuation of an existing game, not an invitation to throw away the project and start from scratch.

**Implement the expansion. Do not stop after providing a plan or design document.**

First inspect the current project, understand its architecture, and identify which systems already exist. Preserve working functionality wherever possible. Integrate the new features into the existing game, refactor only where necessary, and verify that the new systems work together.

If a requested feature cannot be fully implemented or tested in your available environment, implement as much as is possible and document the exact remaining limitation. Never pretend a feature is complete when it is only represented by placeholder code.

---

# 1. THE NEW PRODUCT VISION

SHIFT ZERO is a colorful, chaotic, cooperative industrial game in which players maintain a gigantic malfunctioning factory machine.

Players must react to increasingly difficult emergencies, solve dedicated minigames, purchase helpful utility items, earn persistent progression, collect cosmetic equipment, and survive a long industrial shift.

The experience should feel like a polished, highly replayable Roblox simulator crossed with a cooperative party game.

Its presentation should use the energetic visual language of successful cartoonish Roblox games: oversized objects, saturated colors, exaggerated proportions, glossy materials, expressive animations, bold UI, immediate feedback, and satisfying rewards.

However, this must remain an original, carefully designed experience rather than a low-quality clone.

The primary goals of this expansion are:

1. Expand the existing gameplay map and substantially improve its environmental detail.
2. Build a beautiful, dedicated industrial-themed matchmaking lobby.
3. Implement six matchmaking modes: Solo, Duo, Trio, and teams of four, five, or six.
4. Transport each queued group into the same match server without separating its members.
5. Replace short rounds with a match designed to last approximately 20 minutes.
6. Give every random factory malfunction its own dedicated, playable minigame interface.
7. Introduce a smoothly escalating difficulty curve.
8. Add an intuitive in-game utility shop with useful, carefully balanced items.
9. Implement a collectible case-opening system with cosmetic rarity tiers and satisfying animations.
10. Make the entire experience visually cohesive, intuitive, optimized, and maintainable.

The game must support parties of one to six players, with difficulty and workload adapted to the number of participants actually in the match.

# 2. FIRST: AUDIT THE EXISTING PROJECT

Before modifying code, inspect the entire current development workspace.

Determine:

- How the current map is constructed.
- Where the shift system is implemented.
- How the existing task and malfunction systems work.
- Which remote events, modules, data structures, and UI controllers already exist.
- Whether the project uses Rojo or another established workflow.
- Which assets and asset-generation tools are actually available.
- How player progression and persistence are currently stored.
- Whether the project already has a lobby or a separate match Place.
- Which features are functional and which are incomplete.

Write a short implementation plan and then proceed with implementation.

Do not replace working systems with new implementations merely because a rewrite appears simpler.

Preserve existing player data where practical. If the data schema must change, implement an explicit, backwards-compatible migration strategy.

Replace the old short-round flow with the new approximately 20-minute match format. Replace any former eight-player assumptions with the new configurable maximum of six players per match.

---

# 3. VISUAL OVERHAUL: DISTINCTIVE CARTOON ROBLOX STYLE

This is one of the highest-priority requirements.

The current or previous visual style must be upgraded into a distinctive, polished, cartoon-industrial aesthetic inspired by the visual energy of popular Roblox simulator and progression games.

Do not confuse this with simply increasing brightness or scattering colorful Parts around the map.

## 3.1 Art direction

Create a recognizable visual identity using:

- Bold, oversized environmental silhouettes.
- Exaggerated industrial machinery.
- Chunky mechanical components.
- Thick-looking pipes, oversized valves, large pressure gauges, and massive reactor parts.
- Rounded industrial shapes combined with angular hazard-striping.
- Saturated yellow, safety orange, cyan, teal, deep navy, and controlled neon accents.
- Glossy painted metal, rubber, enamel, plastic, and brushed-metal material contrast.
- Strong silhouettes that remain readable from a distance.
- Stylized lighting and restrained emissive materials.
- Oversized hazard signs and animated warning indicators.
- Expressive environmental animations.
- Satisfying interaction, purchase, unlock, and reward effects.

Use a consistent palette rather than assigning random colors to every object.

The factory should feel like a coherent fictional brand. Its machinery, doors, signage, UI, collectibles, and effects should clearly belong to the same world.

Important interactive objects must stand out from the background.

Create visual hierarchy using scale, contrast, lighting, shape, and deliberate placement.

## 3.2 Cartoonish presentation

The game should feel lively and slightly absurd, while retaining enough visual structure for players to understand the machinery.

Examples include enormous coolant tanks, comically oversized warning buttons, chunky magnetic devices, colorful pipes, mechanical doors with expressive movements, and machine components that visibly wobble before failing.

Use exaggerated but readable animations:

- Machinery starts shaking before a major malfunction.
- Pressure gauges move visibly when pressure changes.
- Valves rotate with clear feedback.
- Reactor panels glow more intensely as instability rises.
- Successful minigames produce satisfying visual confirmation.
- Failed minigames trigger a short, humorous consequence animation.

Keep all effects consistent with the established art direction.

Use procedural Roblox geometry or existing legitimate assets where appropriate. If Forge GUI or another asset-generation tool is connected and accessible, use it for suitable visual assets. Do not claim to have used a tool that is unavailable, invent asset IDs, or rely on assets that the project cannot actually load.

Do not copy another game's logos, maps, character designs, proprietary assets, or distinctive interfaces.

## 3.3 Thumbnail and first-impression quality

Design the central machine and lobby around strong, instantly recognizable silhouettes.

A screenshot should communicate that this is a chaotic factory game even without explanatory text.

Prioritize the first impression from the Roblox game page, the lobby spawn, and the first malfunction.

Avoid generic empty rooms, excessive flat gray surfaces, tiny decorative machinery, and default-looking interfaces.

---

# 4. EXPAND THE PLAYABLE FACTORY MAP

Expand the existing factory into a connected, believable, visually rich environment.

Do not merely make the map larger by adding empty space.

The expanded map must have purposeful traversal, recognizable landmarks, distinct gameplay zones, shortcuts where appropriate, and clear navigation.

## 4.1 Required zones

Build or expand the following areas, adapting them to the current project architecture.

### A. Central Reactor Hall

The visual centerpiece of the game.

Include:

- A massive central machine or reactor.
- Rotating components and animated mechanical sections.
- Several task stations.
- Conveyor systems.
- Large stability indicators.
- Readable malfunction warning displays.
- Accessible routes around the machinery.
- Multiple elevations without confusing the navigation.

The reactor should dominate the room visually while leaving sufficient space for multiplayer interaction.

### B. Electrical Control Wing

Include electrical panels, circuit-routing stations, large breakers, warning lights, and distinctive electrical hazards.

This zone should support electrical and calibration minigames.

### C. Cooling and Pressure Wing

Include coolant tanks, pipes, gauges, valves, cooling systems, and areas where steam or temperature effects can occur.

Provide recognizable locations for cooling and pressure-related malfunctions.

### D. Conveyor and Component Warehouse

Include multiple belts, component storage, item racks, pickup areas, and mechanical transport systems.

Provide clear spaces for retrieving and transporting objects without players becoming stuck between environmental parts.

### E. Maintenance Workshop

Include benches, repair stations, tool displays, spare-part containers, and visual connections to the utility shop's equipment.

### F. Observation and Control Deck

Create an elevated area overlooking the main machine.

It should reinforce the scale of the factory and offer a useful visual landmark. Use railings and collision appropriate to the layout.

## 4.2 Environmental storytelling

Add signs, lighting, markings, hazard stripes, posters, machinery labels, pipes, vents, and mechanical details that make the world feel intentionally constructed.

Use consistent visual language to distinguish:

- Safe areas.
- Interactable machinery.
- Hazardous machinery.
- Queue or transport zones.
- Objective locations.
- Areas temporarily affected by a malfunction.

Decorative objects must not obscure essential objectives.

## 4.3 Navigation

Create simple, intuitive directional cues.

Players should be able to locate an active objective without wandering through the map aimlessly.

Use combinations of:

- Directional indicators.
- Brief waypoint markers.
- Distinctive station colors.
- World-space objective markers.
- Map or zone indicators in the HUD.

If a minimap is appropriate to the existing project, add one that displays the principal rooms and objective locations without filling the screen.

Do not require a large open-world navigation system. The level should remain a compact, highly readable industrial play space with multiple connected areas.

## 4.4 Performance

Use efficient static geometry and sensible collision.

Avoid excessive numbers of individual Parts, unanchored decorative objects, and unnecessary physics simulation.

Use low-cost visual details for distant machinery.

Inspect the completed map for invisible obstacles, accidental collision traps, clipping, missing spawn locations, and inaccessible objectives.

---

# 5. A DEDICATED INDUSTRIAL MATCHMAKING LOBBY

Create a visually impressive, separate-feeling lobby area with its own identity and clear organization.

The lobby is a social waiting area and matchmaking hub, not part of the active factory shift.

## 5.1 The caution-box concept

The main attraction is a dedicated matchmaking hall containing six physical queue enclosures.

These enclosures should resemble oversized industrial safety zones constructed from translucent yellow panels, black-and-yellow hazard stripes, metallic framing, and animated holographic borders.

Imagine a futuristic factory safety checkpoint combined with cartoonish Roblox visual design.

The boxes must be immediately recognizable as places where players enter to queue.

Use translucent panels without making the enclosure visually confusing or difficult to see through.

Each enclosure should have:

- A floor zone that identifies the queue boundary.
- Yellow-and-black industrial striping.
- A readable title above it.
- A live player counter.
- A visible countdown.
- A distinct capacity indicator.
- An animated state when players enter.
- An obvious indication when the queue is full or about to launch.

The boxes should feel satisfying to enter, with subtle lighting, a short activation effect, and clear feedback when the server registers a player.

## 5.2 Six queue enclosures

Implement these exact game modes:

| Queue | Target capacity |
|---|---:|
| Solo | 1 player |
| Duo | 2 players |
| Trio | 3 players |
| Team 4 | 4 players |
| Team 5 | 5 players |
| Team 6 | 6 players |

Scale the physical enclosure sizes to their intended capacities.

The Solo enclosure should be compact. Larger queue enclosures should have enough room for their intended number of players without overlap or uncomfortable crowding.

Use careful spatial arrangement, directional signage, floor markings, and different overhead lighting so that players can immediately identify the correct queue.

The area dedicated to the queue enclosures should be separate from the rest of the lobby. Players should not confuse decorative platforms, the cosmetic showcase, or ordinary floor areas with matchmaking zones.

## 5.3 Lobby aesthetic

The lobby should be beautiful enough that players enjoy remaining in it between matches.

Create:

- A prominent industrial welcome structure.
- A recognizable central visual landmark.
- Animated machinery in the background.
- The matchmaking enclosure area as its own organized zone.
- A cosmetic showcase.
- A route to the collection and shop interfaces.
- A clear view of the queue boxes from spawn.
- A readable atmosphere without visual clutter.

Use the same yellow-and-black safety aesthetic found in the factory, but give the lobby its own clean lighting and a more welcoming composition.

Add visual polish to the ground, walls, ceilings, overhead machinery, and distant scenery. Do not leave large empty gray rooms.

---

# 6. QUEUE BEHAVIOR AND MULTIPLAYER TELEPORTATION

The queue system is a fundamental gameplay feature and must be implemented on the server.

Do not fake queues using client-side counters or merely move players to another part of the same public lobby.

## 6.1 Entering a queue

When a player enters an enclosure:

1. The server validates that the player is eligible to join.
2. The player is added to that queue.
3. The lobby UI updates to show the current queue occupancy.
4. A visible countdown begins if one is not already running.
5. The player receives immediate confirmation that the queue accepted them.

Prevent one player from occupying multiple queues simultaneously.

Remove a player from the queue when they exit its zone, leave the server, or explicitly cancel.

Handle players entering and leaving rapidly without duplicated entries, stale player counts, or broken countdowns.

## 6.2 Countdown rules

Make timing configurable, but start with these defaults:

- **Solo:** launch approximately five seconds after a player successfully enters.
- **Duo through Team 6:** start a maximum waiting timer of approximately 20 seconds after the first player enters.
- If a queue reaches its exact intended capacity before timeout, lock the group and start a short final countdown of approximately three seconds.
- If the waiting timer expires with at least one player still inside, launch with the available players rather than forcing an indefinite wait.
- Show the actual number of players who will enter the match.

For example, a Trio queue with two players after timeout should visibly display that the match is launching with two participants, and the match must scale its difficulty accordingly.

The queue must never silently add an unwanted player or split the queued group.

During the final countdown, freeze the queued player list logically. If a player disconnects or becomes invalid, handle the change safely and reevaluate whether the queue should proceed.

## 6.3 Queue ownership and concurrency

A queue group must be managed atomically on the server.

Prevent two matchmaking enclosures from reserving or teleporting the same player.

Every player must have no more than one active queue membership.

When a group is ready, mark the players as being processed before attempting teleportation. Release these reservations if the teleport fails and restore a usable queue state.

Handle simultaneous queue updates without race conditions.

## 6.4 Reserved match servers

When a queue launches, every player in that group must be transported into the same match instance.

Use Roblox's server-side TeleportService workflow and reserved servers where supported.

Prefer a dedicated Match Place within the same Roblox experience, using a real configured PlaceId.

If the project currently has only one Place and cannot create a second automatically, implement a clearly documented same-Place reserved-server fallback, with configuration that distinguishes a lobby instance from a match instance.

Never invent a PlaceId.

Use actual configured values and document exactly where I must supply any missing PlaceIds.

Use an appropriate group teleport method with the reserved-server access code so the players are sent together.

Do not issue independent matchmaking requests for individual players in the same queue group.

Handle teleport failure callbacks, player disconnects, invalid destination configuration, and retry behavior without trapping players in a permanent loading state.

Use TeleportData only for appropriate session-routing information. Never trust TeleportData, a client remote, or client-side attributes as proof of currency, purchases, or rewards.

The match server must initialize its own authoritative game state after the group arrives.

Important: reserved-server teleportation must be tested in a published Roblox experience because Studio playtesting does not fully support the TeleportService workflow. Document how to test this properly.

---

# 7. SIX PLAYER MODES AND PARTY-SIZE BALANCING

The actual number of players in the match, not merely the queue's nominal capacity, determines difficulty.

A two-player match must not inherit the task workload intended for a six-player team.

## 7.1 Solo mode

Solo mode must be genuinely playable from start to finish.

Use:

- A reduced task workload.
- A forgiving early-game timer.
- No simultaneous emergency requirements that demand two independent players.
- A limited number of active malfunction objectives.
- Additional clarity in minigames when only one player can respond.
- Reasonable stability penalties for individual mistakes.

Do not make solo mode feel like an unfairly difficult version of multiplayer.

## 7.2 Duo and Trio

For two or three players:

- Scale the number of active emergencies down.
- Allow players to complete objectives independently.
- Introduce shared tasks that benefit from teamwork.
- Avoid simultaneous time-critical requirements that cannot be handled by the available players.
- Increase coordination demands gradually rather than doubling the difficulty abruptly.

## 7.3 Teams of four to six

Larger teams can handle more complex workloads.

Introduce:

- Multiple tasks that can be solved in parallel.
- Optional support responsibilities during major emergencies.
- Slightly more frequent event opportunities.
- More varied cooperative task combinations.

Do not make larger parties feel as if they are being punished simply for having more members.

## 7.4 Initial concurrency limits

Use these as default balancing guardrails:

- Solo: never more than one active critical malfunction requiring immediate resolution.
- Duo: normally one active critical malfunction; introduce secondary work only when it is not simultaneously time-critical.
- Trio: primarily one critical malfunction, with carefully introduced parallel support tasks.
- Teams of four to six: allow parallel objectives, but cap simultaneously active critical malfunction minigames at two.

Keep these limits configurable and validate them through testing.

Every individual minigame and every combined event schedule must remain feasible for the actual player count.

---

# 8. REPLACE SHORT ROUNDS WITH A TWENTY-MINUTE MATCH

The central game experience should now be an extended factory shift lasting approximately 20 minutes.

Do not retain the old three-minute shift reset as the main match structure.

One match should be a continuous industrial survival and repair experience consisting of escalating emergencies, tasks, small recovery windows, rewards, and a final challenge.

## 8.1 Match lifecycle

Implement:

1. Match initialization.
2. A short opening sequence.
3. An introductory phase with accessible tasks.
4. A progressively challenging main phase.
5. A late-game emergency phase.
6. A final large-scale factory challenge around minute 20.
7. A results screen.
8. Rewards and progression.
9. A clean transition back to the lobby.

Target an approximately 18–22 minute experience for a full, reasonably successful run, with 20 minutes as the intended duration.

A badly managed team may fail early, but one isolated mistake must not instantly destroy an otherwise playable match.

## 8.2 Failure handling

Mistakes should increase instability, waste time, or create a temporary complication.

A single failed minigame should normally cause a manageable consequence rather than immediate match termination.

Repeated failures can create a critical situation and eventually cause a meltdown.

Provide recovery opportunities that allow a team to regain stability through successful gameplay.

A failed match should still award reasonable participation rewards, adjusted for actual contribution and progress.

Never erase permanent progression because the group failed its shift.

## 8.3 Difficulty progression

Difficulty must increase smoothly throughout the match.

The fifth minute should feel accessible, understandable, and reasonably forgiving.

By the fifteenth minute, players should clearly feel that the factory has become significantly more demanding.

The increase must be noticeable but gradual, not a sequence of sudden unfair spikes.

Use a centralized difficulty model based on actual elapsed match time.

A reasonable initial model is:

`t = clamp(elapsedSeconds / 1200, 0, 1)`

`difficultyMultiplier = 1 + 1.5 * (t ^ 1.6)`

Treat this as a configurable starting point and calibrate it through testing.

This produces an approximate difficulty multiplier of:

- Minute 0: 1.00
- Minute 5: 1.16
- Minute 10: 1.50
- Minute 15: 1.95
- Minute 20: 2.50

The multiplier is a tuning signal, not permission to make every game parameter scale indiscriminately.

Use it to influence appropriate values such as:

- Minigame pattern complexity.
- Number of steps.
- Time available for a task.
- Timing-window tolerance.
- Movement speed in skill-based challenges.
- Length and variety of input sequences.
- Frequency of malfunction events.
- Required repair effort.
- Probability of more complex event combinations.

Do not automatically multiply all damage, event count, task count, or movement speed by the same factor.

Clamp every parameter within a tested minimum and maximum.

Maintain a smooth progression curve between phases. Avoid changing from an easy encounter directly to an extremely difficult encounter on a single timer boundary.

## 8.4 Difficulty and accessibility

Increase complexity without making controls unreliable.

Players must still have time to understand the minigame, read the instructions, and react to the challenge.

Late-game difficulty should come from longer patterns, more careful decisions, narrower but fair timing windows, and more demanding coordination—not from unreadable text, instantaneous failure, or excessive screen clutter.

Randomness must remain bounded.

If a team fails one difficult emergency, the system must not immediately generate an impossible sequence of emergencies because instability rose.

Implement explicit limits on event stacking, short recovery opportunities, and minimum reaction times.

## 8.5 Final phase

Around minute 18–20, introduce a visually impressive final challenge involving the central reactor.

Combine familiar mechanics in a new sequence so that the climax feels earned.

Use several escalating stages, readable warning indicators, and meaningful success feedback.

Scale the number and complexity of stages according to the actual team size.

The match should end with a memorable conclusion and a polished results screen, not an abrupt timer disappearing.

---

# 9. EVERY RANDOM FACTORY MALFUNCTION MUST HAVE ITS OWN MINIGAME

This is a strict design requirement.

Every random event or factory malfunction must launch a dedicated, playable minigame interface that directly corresponds to the problem being solved.

A generic popup saying "Press E to repair" is not sufficient.

A generic minigame reused unchanged for every event is also not sufficient.

Create a reusable technical framework for minigames, but give each malfunction its own mechanics, visual language, and interaction pattern.

## 9.1 Event-to-minigame mapping

Implement at least the following mappings.

### Event A: Electrical Overload

**Minigame: Circuit Routing**

Players connect electrical nodes in the correct sequence.

Visuals should feature a stylized circuit board, glowing nodes, animated current, and clearly distinguishable connection paths.

As difficulty rises, introduce longer sequences and additional plausible routes while keeping the correct solution readable.

### Event B: Cooling Failure

**Minigame: Pressure and Temperature Regulation**

Players operate a combination of valves or sliders to keep pressure and temperature inside a target range.

The gauges should respond visibly to player inputs.

Higher difficulty introduces interacting controls, faster drift, and a more demanding target range, within reasonable limits.

### Event C: Conveyor Jam

**Minigame: Component Alignment**

Players identify jammed components and move or rotate them into the correct alignment while the conveyor produces controlled movement.

The player must interact with mechanical geometry rather than simply select an arbitrary text button.

Increase complexity using additional component orientations and more demanding, but fair, timing.

### Event D: Magnetic Outburst

**Minigame: Magnetic Stabilization**

Players guide unstable metal components into designated safe positions while magnetic fields pull them away from their intended paths.

Use a visually clear play area with animated force indicators and an identifiable target.

Difficulty may increase through controlled changes in pull strength, path complexity, and the number of objects.

### Event E: Gravity Surge

**Minigame: Gravity Calibration**

Players synchronize a moving indicator, stabilize a floating component, or complete a timed sequence of mechanical adjustments.

Make the changing gravity easy to understand visually.

Increase the complexity of the sequence gradually, not by removing necessary reaction time.

### Event F: Oversized Components

**Minigame: Precision Calibration**

Players adjust the size, position, or rotation of a component until it matches a displayed target.

Use a clear ghost silhouette or target outline.

Higher difficulty introduces more precision and additional stages.

### Event G: Emergency Shutdown

**Minigame: Breaker Sequence**

Players identify and activate the correct sequence of breakers to restore the machine.

Use recognizable switch shapes, illuminated states, directional cues, and readable feedback.

Increase sequence length and introduce more complex but logically generated patterns over time.

### Event H: Pressure Leak

**Minigame: Emergency Valve Routing**

Players identify the leaking line and activate the correct valve sequence before the pressure gauge enters a critical state.

Higher difficulty introduces branching pipe routes and more complicated sequences.

Do not turn the game into an unreadable maze.

## 9.2 Extensible event architecture

Every event definition must explicitly reference a valid minigame definition.

Use a data-driven architecture containing, at minimum:

- Event identifier.
- Display name.
- Warning duration.
- Visual and audio configuration.
- Player-count constraints.
- Minigame identifier.
- Difficulty parameters.
- Success outcome.
- Failure outcome.
- Stability effects.
- Reward effects.
- Cleanup behavior.

Add a development-time validation step that detects an event without a corresponding minigame implementation.

It must not silently fall back to a generic repair button if the event definition is incomplete.

## 9.3 The minigame interface

Design a shared, reusable minigame screen with event-specific presentation.

The interface should include:

- A clear title identifying the emergency.
- A short, actionable instruction.
- The relevant visual puzzle or interaction area.
- A progress indicator.
- A timer when appropriate.
- A readable success condition.
- Immediate visual feedback.
- A result transition.
- An optional accessibility hint, where appropriate.

The minigame should occupy the player's visual focus without making the whole HUD unreadable.

It must adapt to desktop, mobile, and supported controllers.

Do not rely on tiny drag targets, hover-only mechanics, keyboard-only interactions, or interactions that are impossible to perform through touch.

## 9.4 Multiplayer interaction

Determine whether an event is best implemented as a shared team minigame or as a minigame assigned to the affected player.

The design must remain consistent with the event and the player count.

If several players are involved, display clear participation cues so they understand whether they are helping the same objective or solving a separate task.

Do not make every player solve the exact same simultaneous time-critical puzzle unless the event is intentionally designed for that scenario.

All shared completion, rewards, and failure effects must be validated by the server.

A client must never be able to send a simple "I won" remote request and automatically complete an emergency.

Validate the required interactions, sequence progression, timing constraints, and permitted state transitions on the server.

## 9.5 Event lifecycle and cleanup

Every minigame must have clear start, success, failure, timeout, and interruption states.

Closing the interface, leaving the server, disconnecting, or encountering a match transition must not leave the event permanently active.

When an event ends, restore every altered environmental property and remove temporary effects.

Prevent duplicate rewards and duplicate completion requests.

---

# 10. EVENT FREQUENCY AND TEAM WORKLOAD

The game should become more demanding both because minigames become more complex and because emergencies occur more regularly as the match progresses.

However, an increase in event frequency must be coordinated with the number of players.

Implement configurable ranges for the intervals between new events.

Start with approximately:

- Solo: 55–70 seconds early in the match, decreasing toward 38–50 seconds late in the match.
- Duo: 50–65 seconds early, decreasing toward 35–45 seconds late.
- Trio: 45–60 seconds early, decreasing toward 32–42 seconds late.
- Teams of four to six: 40–55 seconds early, decreasing toward 27–38 seconds late.

These are initial tuning ranges, not immutable values.

Apply controlled random variation within the configured ranges.

Do not start a new critical event solely because a timer expired if doing so would produce an unmanageable combination of existing emergencies.

Use scheduling rules that consider:

- Actual player count.
- Current instability.
- Current active events.
- Time until each existing event expires.
- Current minigame difficulty.
- Recent failed events.
- The need for occasional recovery.

At higher difficulty, vary the type of challenge and the required decisions rather than simply spawning more hazards.

The match director must always respect explicit limits on simultaneous critical events.

---

# 11. IN-GAME UTILITY SHOP

Implement an intuitive utility shop accessible through the main game UI.

This shop is different from the cosmetic case system.

It sells deterministic items that help players manage emergencies. The player must know exactly what an item does and what it costs before purchasing it.

The default utility economy should use **Bolts earned through gameplay**, not purchased randomized power.

## 11.1 Initial inventory

Implement these starter utility items.

### Emergency Patch

- Restores a small amount of machine stability.
- Suggested starting effect: +4 stability, capped at 100.
- Limited uses per player per match.
- Does not prevent a team from losing through repeated mistakes.

### Diagnostic Scan

- Reveals a small hint for the currently active minigame.
- Must not automatically solve the puzzle.
- Has a cooldown or a limited number of uses.

### Cooling Charge

- Adds approximately two seconds to an eligible cooling-related minigame.
- Cannot stack indefinitely.
- Should not make a critical minigame trivial.

### Component Finder

- Highlights one relevant component during a recovery or conveyor event.
- Does not teleport the component into the player's inventory.
- Has limited uses or an appropriate cooldown.

### Reinforced Gloves

- Provides a modest temporary improvement to a suitable carrying or interaction mechanic.
- Must not bypass the actual interaction or remove the need for teamwork.

Implement the items as configurable data entries rather than separate hardcoded purchasing systems.

Tune prices through playtesting.

## 11.2 Shop UI

Create an attractive, polished shop panel with:

- Item icon or distinctive visual.
- Item name.
- Clear description.
- Price in Bolts.
- Current inventory or available uses.
- Purchase button.
- Immediate purchase feedback.
- Insufficient-currency feedback.
- A readable distinction between consumables and persistent upgrades.

Players should be able to understand the value of an item without guessing.

Do not make the shop automatically open every few seconds.

During an active minigame, purchases and interface interactions must not interrupt the challenge or conceal essential controls. Purchases may be made outside the minigame, and usable items must respect their configured activation conditions.

## 11.3 Fair progression

Every functional utility item must have a reasonable earnable path.

Do not create an intentionally frustrating free experience to pressure players into spending Robux.

Limit the number of uses and the strength of effects so that purchases remain helpful without guaranteeing a win.

Players who spend no Robux must retain a complete and viable progression path.

By default, utility purchases should be made with Bolts. If Robux-funded utility products are added later, make them optional, modest in effect, and subject to a reasonable free alternative. Do not sell an exclusive, substantially stronger tool.

## 11.4 Security

The server must validate every utility purchase and use.

Check the real server-side Bolts balance, item price, inventory, availability, cooldowns, and session limits.

Never accept a client-supplied price, amount of currency, or arbitrary reward effect.

Deduct currency and grant the item atomically as far as the selected persistence architecture allows.

Prevent duplicate purchasing requests, negative balances, repeated item use, and exploitation through rapid remote calls.

---

# 12. CASE OPENING AND COSMETIC GACHA SYSTEM

Create a polished collectible case system inspired by the excitement and reveal sequence of popular game cases, including Counter-Strike-style rarity presentation.

Use the general mechanic as inspiration, but develop an original visual identity appropriate to SHIFT ZERO.

Do not copy Counter-Strike case art, UI layouts, logos, audio, weapon skins, or other protected assets.

The cases should feel like industrial containers recovered from different factory sectors.

## 12.1 Case themes

Create several data-driven case types, such as:

- **Scrap Case:** industrial basic cosmetics.
- **Reinforced Case:** improved-looking tool and uniform cosmetics.
- **Prototype Case:** futuristic experimental equipment.
- **Quantum Case:** premium-looking reactor-themed cosmetics.

These names are examples. Refine the branding to fit the game's style.

Each case must have an explicitly defined reward pool and probability table.

Do not make the case system produce functional combat or repair advantages.

## 12.2 Cosmetic-only rewards

Case rewards must be cosmetic, including:

- Tool skins.
- Uniforms.
- Helmets and accessories.
- Decorative nameplates.
- Emotes.
- Victory animations.
- Cosmetic particle effects.
- Workshop decorations.
- Machine appearance themes.

Cases must not grant the strongest functional equipment, mandatory gameplay upgrades, exclusive emergency solutions, or competitive advantages.

All actual gameplay utility should remain separately earnable through ordinary progression.

## 12.3 Opening animation

Create a satisfying opening sequence:

1. The player selects an eligible case.
2. The interface displays its reward pool.
3. The player confirms the opening.
4. A short, polished animation presents the possible cosmetic rewards.
5. A reveal animation highlights the actual reward.
6. The server grants the authoritative reward.
7. The interface displays its name, rarity, appearance, and next actions.

The reveal should feel dramatic but remain reasonably quick.

Let the player skip or shorten repeated animations after the initial reveal.

Never determine the reward based on client-side animation timing or the cosmetic shown at a particular frame.

The server must select the actual reward using the configured probabilities. The client animation must reveal the server-selected result rather than choose it.

## 12.4 Rarity presentation

Implement a coherent rarity hierarchy with distinct colors, effects, and visual treatments.

A proposed hierarchy is:

- Common.
- Uncommon.
- Rare.
- Epic.
- Legendary.

Rarity styling must be distinguishable without depending entirely on color.

Show the cosmetic's name, rarity, and a visual preview where available.

Avoid flashing effects that make the experience inaccessible or hide the actual reward.

## 12.5 Starter probability configuration

Implement one complete starter case using an exact, data-driven probability table.

The initial case may contain 13 individual cosmetic outcomes:

- Six Common cosmetics, each with a 10% probability.
- Three Uncommon cosmetics, each with a 7% probability.
- Two Rare cosmetics, each with a 6% probability.
- One Epic cosmetic with a 5% probability.
- One Legendary cosmetic with a 2% probability.

These individual probabilities sum to exactly 100%.

Create the actual cosmetic definitions and use the table as the authoritative source for both server selection and UI disclosure.

Do not display only rarity-level percentages when individual item odds must be disclosed.

When additional cases are added, give each case its own explicit, validated table.

Add a development-time assertion that rejects probability tables whose final outcomes do not sum to exactly 100%, allowing for deliberate fixed-point or integer-weight representations.

The user-facing percentages must be accurate and understandable.

## 12.6 Cases earned through gameplay

Players must be able to earn cases through matches, achievements, milestones, and ordinary progression.

Provide a free collection path with desirable cosmetics.

The player must not be required to spend Robux to participate in the collection system.

## 12.7 Paid random cases and Roblox compliance

If paid cases are implemented, treat their restrictions as a core technical requirement.

Roblox policy applies to random items purchased directly with Robux and to random outcomes purchased indirectly through currency or tickets that can be bought with Robux.

Therefore:

- Do not sell Bolts for Robux while assuming that paid cases purchased with those Bolts are automatically exempt from paid-random-item requirements.
- Use PolicyService and the appropriate per-player policy information.
- Respect `ArePaidRandomItemsRestricted`.
- Hide, disable, or replace paid random-item purchases for players who are ineligible.
- Preserve access to free, gameplay-earned cases.
- Offer deterministic direct-purchase alternatives where appropriate.
- Never silently bypass regional or user-specific eligibility restrictions.
- Do not implement paid item trading in the MVP.

Before a paid random purchase, display all possible final outcomes and their actual numerical odds.

Provide a clearly labeled, accessible "Details" or "View Odds" control. A lone information icon without an explanatory label is insufficient.

All disclosed probabilities must accurately reflect the actual server-side reward pool and sum to 100%, subject to permitted rounding disclosures.

If a paid random item's odds can change because some outcomes are no longer obtainable, update the displayed odds accordingly.

If items can be duplicated, disclose the duplicate handling clearly and award a meaningful, fixed reward for duplicates. Never let a paid outcome simply consume payment without providing value.

Do not sell paid luck boosts or probability modifiers in the MVP.

Complete the Roblox Maturity & Compliance questionnaire accurately before publishing a version containing paid random items.

If paid random items cannot be implemented compliantly within the existing architecture, implement gameplay-earned cases first and leave the paid random purchase pathway disabled rather than shipping an unsafe or noncompliant approximation.

## 12.8 Collection UI

Create an inventory and collection screen where players can:

- Inspect owned cosmetics.
- See rarity and item descriptions.
- Equip available cosmetics.
- View newly acquired rewards.
- Track collection completion.
- Preview locked cosmetics, where appropriate.
- See duplicate-conversion rules.

Persist the inventory securely.

Implement server-side ownership checks before allowing cosmetic equipment changes.

Do not assume the client owns an item just because it has displayed an unlock animation.

---

# 13. UNIFIED USER INTERFACE

Refine the whole game's UI into one consistent design system.

The lobby, queue indicators, match HUD, minigames, utility shop, collection, case opening, and results screen must clearly belong to the same game.

## 13.1 Visual UI language

Use a cartoon-industrial design featuring:

- Rounded or chamfered industrial panels.
- Yellow-and-black hazard-striping accents.
- Dark navy or charcoal backgrounds.
- Vivid status colors.
- Clear typography.
- Consistent iconography.
- Subtle gradients and restrained transparency.
- Brief transitions and satisfying interaction animations.

Do not turn every panel yellow and black. Use hazard colors where they communicate danger, status, or industrial identity.

The interface must remain readable during chaotic moments.

## 13.2 Main match HUD

Maintain clear visibility of:

- Machine stability.
- Remaining match time.
- Current task.
- Active malfunction.
- Minigame status when applicable.
- Earned Bolts.
- Utility inventory.
- Team contribution and objectives where useful.

Do not overcrowd the center of the screen.

## 13.3 Matchmaking interface

Every queue enclosure should have a synchronized world-space and screen-accessible representation of:

- Queue type.
- Current occupancy.
- Target capacity.
- Countdown.
- Whether the queue is filling, locked, or transporting players.

Do not rely exclusively on tiny 3D text.

## 13.4 Mobile compatibility

Test the UI at small screen sizes.

Every minigame must have appropriate touch-friendly controls.

Buttons must not overlap, appear off-screen, or become inaccessible behind the Roblox interface.

Ensure that the shop, case-opening UI, and inventory remain usable on both desktop and mobile.

Use controller navigation where appropriate.

Provide clear closing and back-navigation behavior for every major panel.

---

# 14. ARCHITECTURE AND IMPLEMENTATION QUALITY

Continue the existing architecture and adapt it sensibly.

A possible separation of responsibilities includes:

- Matchmaking queue service.
- Queue state and membership management.
- Teleport and match-routing service.
- Match lifecycle service.
- Difficulty director.
- Event scheduling service.
- Malfunction registry.
- Minigame registry.
- Minigame validation service.
- Player inventory and utility service.
- Cosmetic collection service.
- Case reward service.
- Data persistence service.
- UI controllers for lobby, match, shop, and cases.

Use this structure only where appropriate. Do not introduce needless abstraction just to imitate a large commercial codebase.

Prefer clean, typed Luau modules with explicit interfaces.

Keep server-only logic on the server, shared definitions in appropriate shared modules, and presentation logic on the client.

Never place secret or trusted reward logic in replicated client modules.

Maintain clear separation between:

- Temporary match state.
- Persistent progression.
- Cosmetic ownership.
- Functional inventory.
- Queue state.
- Paid purchase state.

Implement cleanup routines so repeated matches do not accumulate connections, objects, timers, or stale state.

If the existing data system requires modification, preserve backward compatibility and provide migration logic rather than overwriting stored player profiles.

---

# 15. QA AND ACCEPTANCE TESTS

Do not declare the expansion complete simply because the project contains new scripts.

Execute all tests that the available environment supports.

## 15.1 Lobby tests

Verify:

- All six matchmaking enclosures exist.
- Each has the correct capacity.
- Player counts update correctly.
- Players cannot occupy multiple queues.
- Leaving a queue removes the player safely.
- A full queue starts the final countdown.
- A partial queue launches correctly after timeout.
- The actual player count is passed into match initialization.
- Queue cancellation and disconnects do not create stuck states.

## 15.2 Teleport tests

Verify, when a published experience is available:

- A full party is transported to the same reserved match instance.
- Members of a queue group are not split across servers.
- Invalid configurations produce readable failure feedback.
- Teleport failures do not permanently lock the queue.
- Match initialization occurs only in the intended destination.
- Lobby instances remain functional after other groups depart.

Document any limitations caused by unpublished Places or unavailable Roblox services.

## 15.3 Match tests

Run or document reproducible tests for:

- Solo.
- Duo.
- Trio.
- Team 4.
- Team 5.
- Team 6.
- A complete approximately 20-minute match.
- Early failure.
- Successful final challenge.
- Match results and returning to the lobby.

Check that smaller groups are not subjected to the same concurrent workload as larger groups.

## 15.4 Difficulty tests

Inspect difficulty at minutes 0, 5, 10, 15, and 20.

Verify that:

- Early play is understandable.
- Minute 5 is manageable.
- Minute 10 feels more demanding.
- Minute 15 is materially harder than minute 5.
- Minute 20 feels appropriately challenging.
- The escalation does not create sudden impossible spikes.
- Random events cannot form unwinnable combinations.
- Recovery remains possible after an isolated failure.

## 15.5 Minigame tests

Test every implemented malfunction.

Verify that its dedicated minigame opens, responds to input, updates progress, and handles success, failure, timeout, disconnection, and interruption correctly.

Check desktop and mobile interactions.

Ensure that each event has a valid minigame definition and that server-authoritative logic prevents fabricated completion requests.

## 15.6 Shop and case tests

Verify:

- Utility purchases deduct the correct amount of Bolts.
- Invalid purchases are rejected by the server.
- Items cannot be used more often than permitted.
- Case reward selection occurs on the server.
- The displayed odds match the reward pool.
- Every case probability table is valid.
- Owned cosmetics and inventory changes persist correctly.
- Duplicate rewards follow the disclosed rules.
- Paid random-item restrictions are respected.
- Unconfigured Robux products cannot grant rewards.
- No client-side request can create currency or cosmetic ownership.

## 15.7 Performance tests

Inspect the expanded map and repeatedly run match transitions.

Check for:

- Unbounded connections.
- Leaked temporary objects.
- Stuck task timers.
- Excessive concurrent event effects.
- Unnecessary physics simulation.
- Severe UI frame-rate drops.
- Missing cleanup after a meltdown.
- Memory growth after repeated shifts.

Run static analysis and any available Luau linting or type checking.

Do not claim that full multiplayer performance has been tested unless it actually has been.

---

# 16. DEVELOPMENT WORKFLOW

Work through the expansion in this order.

### Phase 1: Audit and architecture

Inspect the existing project and identify the minimum changes required.

### Phase 2: Lobby and queue system

Implement the matchmaking hall, all six enclosures, queue tracking, countdowns, and reliable group routing.

### Phase 3: Map and visual overhaul

Expand the map, refine the environment, and introduce the unified cartoon-industrial art direction.

### Phase 4: Match lifecycle and difficulty

Convert the match into the intended 20-minute experience and implement party-size scaling.

### Phase 5: Minigame framework

Implement the registry, event mapping, interfaces, server validation, and cleanup behavior for every malfunction.

### Phase 6: Utility shop

Implement deterministic utility purchases, inventory, effects, security, and interface polish.

### Phase 7: Cosmetic cases

Implement the collection, case data, server-side reward selection, reveal sequence, probability disclosures, and policy gates needed for any paid randomized purchases.

### Phase 8: Integration and QA

Run the available checks, fix identified problems, inspect the complete player experience, and test all supported configurations.

You may adjust the order slightly when dependencies require it, but do not abandon an entire feature merely because another feature is more visually interesting.

Do not endlessly redesign systems that already satisfy their acceptance criteria.

Do not generate an enormous number of extra features before the required systems work reliably.

---

# 17. FINAL DELIVERABLES

When development is complete, provide:

1. The actual modified project files.
2. A summary of the map expansion and visual improvements.
3. The complete matchmaking mode configuration and explanation of how groups reach the same match server.
4. The match duration and difficulty progression implementation.
5. A list of implemented malfunction/minigame pairs.
6. The utility shop inventory and its balancing configuration.
7. The case pool configuration and exact odds-disclosure mechanism.
8. The required Roblox configuration values and any PlaceIds or product IDs that must be supplied manually.
9. A clear procedure for opening and testing the project in Roblox Studio.
10. A test report listing what actually passed, what failed, and what could not be tested.
11. A short list of remaining defects or necessary manual setup steps.

Do not finish with only screenshots, mockups, pseudocode, or a design document.

Do not replace missing functionality with fake buttons that look functional.

Do not claim flawless performance or viral potential.

The result should be a coherent, fully integrated expansion of SHIFT ZERO: KEEP IT RUNNING.

**Begin by inspecting the existing workspace. Then implement the expansion, verify what you can, and repair the issues you discover.**