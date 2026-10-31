# CLAUDE CODE MASTER PROMPT — BUILD A VIRAL-READY ROBLOX EXPERIENCE

You are acting as the lead Roblox game designer, senior Luau engineer, technical artist, UI/UX designer, gameplay systems engineer, and QA engineer for an original Roblox experience.

Your job is not to give me a game design document and stop. Your job is to inspect the current development workspace, implement a complete and playable MVP, verify the code as thoroughly as the available tools allow, fix the problems you identify, and leave me with a project I can open in Roblox Studio and continue developing.

Do not claim to have run Roblox Studio, multiplayer tests, or live-server tests unless you have actually done so. If a test cannot be executed in your environment, explain precisely what remains unverified and provide reproducible testing instructions.

---

# 1. PRODUCT VISION

## Working title

**SHIFT ZERO: KEEP IT RUNNING**

Treat this as a provisional title. If internet access is available, check whether the exact title is already in use on Roblox before finalizing the game's branding. Do not copy another game's identity, assets, interface, maps, code, or distinctive visual designs.

## The one-sentence hook

You and up to seven other players must keep a gigantic, increasingly unstable machine operating while unexpected malfunctions change the rules of the environment.

The machine can reverse conveyor belts, attract loose objects with magnetic forces, alter gravity, overheat, jam, and trigger spectacular but harmless meltdowns.

Players work together, earn resources, unlock progression, collect discoveries, customize their equipment, and return for progressively more challenging shifts.

The experience must be immediately understandable from a thumbnail and the first few seconds of gameplay.

## Market positioning

The game should combine:

- The accessible progression of a simulator.
- The social cooperation of a multiplayer party game.
- The tension of a timed survival challenge.
- The unpredictability and spectacle of a physics-based game.
- A persistent progression system that rewards repeated play.

The current Roblox market demonstrates demand for collectible progression, social experiences, survival, and short, readily understandable gameplay loops. However, generic fishing, factory, egg-stealing, and brainrot-style clones face established competition.

Our differentiator is the combination of a shared machine, readable cooperative tasks, escalating malfunctions, slapstick physics, and persistent customization.

This is a market hypothesis, not a guarantee of success or a claim that no similar games exist.

# 2. NON-NEGOTIABLE DESIGN PRINCIPLES

1. **Playable before enormous.** Build one excellent, complete game loop before adding large amounts of content.
2. **The first task starts almost immediately.** A new player should understand the objective and perform a meaningful action within approximately 10 seconds.
3. **Solo and multiplayer must both work.** Support one to eight players. Scale task requirements to the number of active participants.
4. **Readable chaos, not random punishment.** Every major malfunction must be communicated clearly, with a visual warning before it begins.
5. **Never destroy permanent progress because a team failed a shift.** Failure should create memorable moments, not make players feel their time was wasted.
6. **Mobile is a first-class platform.** Design usable touch interaction from the beginning rather than squeezing a desktop interface onto a phone.
7. **Fair monetization.** Paid content must not create a substantial competitive advantage or make free progression miserable.
8. **Server-authoritative gameplay.** Clients must never control their own rewards, currencies, task completion, or machine stability.
9. **Original presentation.** Develop a coherent art direction, original UI, original environmental composition, and distinctive visual effects.
10. **Verification over empty promises.** Implement, inspect, test where possible, and fix actual issues. Do not claim perfection simply because the code has been generated.

# 3. THE CORE GAME LOOP

## The machine hall

Create one polished, multiplayer industrial environment centered around a gigantic machine.

The room should contain a central reactor or engine, several interactive stations, a conveyor system, loose mechanical components, safety barriers, warning lights, a task display, and a prominent stability meter.

The environment must feel like a deliberately designed game level rather than a collection of default Roblox Parts.

Every player should be able to see what the team is trying to accomplish.

## A. The shift

Each shift lasts approximately three minutes, with tasks and malfunctions becoming more demanding as the team progresses.

Do not force players to sit through a long pre-round lobby. Begin the first task immediately for the first player or group. Players who join an ongoing session should be able to participate safely without breaking the current shift.

Maintain a server-authoritative machine stability value between 0 and 100.

Successful tasks stabilize the machine and reward the team. Incorrect actions, missed deadlines, and certain hazards increase instability.

Display the current objective, time remaining, machine stability, and earned currency through a clean, readable HUD.

If the machine reaches critical failure, initiate a spectacular, short, comedic meltdown sequence. Then restore the room and begin another playable shift. Permanent player progression must survive.

A failed shift should still grant a reasonable participation reward, with better rewards for completing more tasks.

## B. Implement at least six distinct task types

Build these as reusable systems rather than hardcoding each task into one enormous script.

1. **Power rerouting:** activate color-coded power nodes in a displayed sequence.
2. **Component recovery:** locate a loose component, carry it to the correct station, and insert it.
3. **Pressure regulation:** interact with a valve or control to bring a gauge into a target range.
4. **Cooling emergency:** retrieve coolant and deliver it to an overheating machine.
5. **Conveyor repair:** remove a jammed object and restore the conveyor.
6. **Circuit calibration:** solve a short visual matching or timing interaction using a small interface.

Each task must communicate what the player should do, provide immediate feedback, and register completion only after the server validates the action.

Use Roblox ProximityPrompts or equivalent interactions where appropriate, with custom UI where it improves clarity.

Do not make every task a button press. Vary the physical interactions, movement, coordination, and timing sufficiently that the gameplay feels like operating a real, chaotic machine.

## C. Implement at least five malfunction events

Create a modular event system with configurable durations, warning periods, and effects.

Initial event set:

- **Polarity Reversal:** conveyor belts reverse direction.
- **Magnetic Outburst:** loose metal components are attracted toward a clearly marked magnetic zone.
- **Gravity Surge:** gravity or jump behavior changes within reasonable, readable limits.
- **Oversized Components:** selected movable objects temporarily grow dramatically.
- **Emergency Shutdown:** ordinary lighting dims while emergency lights and illuminated objective indicators remain visible.

These are examples of original game events, not rigid limitations. Improve their presentation and implementation as needed.

Requirements:

- Announce each event approximately five seconds before it starts.
- Display an identifiable icon, text label, countdown, and matching world effect.
- Synchronize event state across players.
- Ensure events terminate correctly and restore the affected objects or settings.
- Prevent incompatible events from breaking one another.
- Avoid flashing effects that could harm accessibility or obscure essential information.
- Do not use unpredictable input inversion or other effects that make mobile controls unusable.

Trigger a new event approximately every 45–60 seconds, with controlled variation. Do not stack multiple disruptive events in ways that make objectives impossible.

Create a centralized configuration system so new tasks and events can be introduced without rewriting the underlying game loop.

## D. Scale for player count

Make the experience fully playable with one player.

Reduce simultaneous task requirements and time pressure when fewer players are present. Allow larger teams to handle multiple tasks in parallel and introduce slightly more demanding combinations.

Do not make players depend on strangers to perform a mandatory action that cannot reasonably be performed alone.

Reward meaningful individual contribution while preserving the cooperative nature of the game. Prevent idling, duplicate remote requests, and other trivial reward exploits.

# 4. PROGRESSION AND RETENTION

The game must offer reasons to play another shift beyond repeatedly pressing buttons for currency.

## Persistent progression

Implement a permanent currency called **Bolts**.

Players earn Bolts through task completion, shift performance, first-time discoveries, and appropriately balanced challenges.

Use Bolts to unlock:

- New tool appearances.
- Machine cosmetic themes.
- Character uniforms and accessories designed specifically for the experience.
- Titles and nameplate decorations.
- Personal workshop decorations.
- Additional entries in a discovery collection.
- Earnable gameplay upgrades, balanced for the cooperative environment.

Gameplay upgrades must be earnable without Robux. Purchases must not grant exclusive access to the strongest equipment.

Do not implement enormous upgrade trees in the MVP. Start with a compact, meaningful progression structure, and ensure prices and rewards are configurable.

## Collection system

Create a discovery journal tracking tasks completed, malfunction types encountered, shift milestones, and other achievements.

Display progress clearly. Unlock cosmetic rewards for exploration and achievement, rather than requiring players to purchase randomized loot.

Include a few attainable milestones and several longer-term goals.

## Daily and weekly replayability

Implement a lightweight challenge framework if it fits the existing architecture:

- A daily objective.
- A rotating shift modifier.
- A weekly team milestone.
- A reward for completing a particularly clean or difficult shift.

Do not make the MVP dependent on a complicated live-service backend. The core experience must function even if daily or weekly challenges are unavailable.

Avoid punishing login streaks, forced waiting periods, or artificial energy systems.

## Social gameplay

Create moments that make players want to invite friends:

- Cooperative task bonuses based on actual participation.
- A clear team performance summary after a shift.
- Funny descriptions of the malfunction that caused a failure.
- Earnable titles for memorable achievements.
- Celebratory animations that players can use together.

The game should remain enjoyable without voice chat. Use visual cues and clear objectives to communicate essential information.

# 5. VISUAL DIRECTION: POLISHED, ORIGINAL, AND RECOGNIZABLE

The experience must look deliberately art-directed. Do not settle for a functional but visually empty prototype as the final MVP.

## Environment

Create a stylized industrial science-fiction setting with a playful, slightly absurd tone.

Use:

- Strong silhouettes and readable mechanical shapes.
- Layered industrial architecture.
- Oversized pipes, pistons, conveyors, pressure chambers, and control panels.
- High-quality material contrast.
- Emissive elements for important interactive components.
- A carefully controlled lighting setup with Atmospheric effects where appropriate.
- Distinct colors for task types, hazards, and machine states.
- Environmental details that reinforce scale and personality without cluttering gameplay.

Use original geometry built from Roblox Parts, meshes already present in the project, or other assets that are legitimately available. Do not fabricate asset IDs or depend on missing assets.

Keep visual performance appropriate for mobile devices.

## Animation and visual effects

Build effects that make the machinery feel alive:

- Rotating mechanical components.
- Sliding panels and moving pistons.
- Conveyor movement.
- Warning lights and readable alarms.
- Small sparks and smoke effects.
- Controlled steam bursts.
- Magnetic attraction effects.
- Component growth and shrinking animations.
- Reactor instability effects.
- A short, satisfying meltdown sequence.
- Clear success and failure feedback.

Use TweenService, particle emitters, beams, constraints, and other appropriate Roblox systems.

Effects must have clear start and end states. Restore modified objects after every event and destroy temporary instances when they are no longer needed.

Do not use excessive particles, uncontrolled physics objects, or hundreds of continuously running loops.

## Sound

Inspect the existing project for usable audio assets. Use properly available assets if present. Do not invent audio asset IDs.

If suitable audio is unavailable, finish the functional and visual game first and document the exact audio assets that would improve it.

Essential tasks must never depend solely on sound for feedback.

# 6. UI/UX REQUIREMENTS

Design a cohesive interface rather than combining unrelated default Roblox menus.

The core HUD should include:

- Machine stability.
- Shift timer.
- Current task and clear instructions.
- Active malfunction and time remaining.
- Bolts balance.
- Task completion feedback.
- Interaction prompts.
- A compact progression or collection menu.
- A configurable cosmetics shop.
- A post-shift results screen.

The interface must work on desktop, mobile, tablet, and controller where Roblox supports the relevant input.

Use responsive layouts and account for screen safe areas. Keep important touch targets large enough for phones. Avoid small text, crowded overlays, and menu elements that compete with the central gameplay.

Provide visible feedback for every important player action.

Support reduced visual effects where practical.

Create a concise first-time onboarding sequence that teaches players how to perform an interaction and complete their first task without making them sit through a long tutorial.

# 7. MONETIZATION: ETHICAL AND FUNCTIONAL

The game is free to play. Design its monetization around self-expression, customization, and optional convenience rather than domination over other players.

## Potential paid items

Implement the infrastructure so the following can be added once real Roblox product IDs are available:

- Cosmetic tool skins.
- Character uniforms.
- Special emotes and victory animations.
- Machine appearance packs.
- Workshop decoration themes.
- Nameplates and titles.
- Cosmetic effects for successful task completion.
- Additional saved cosmetic loadout slots.
- Optional private-server customization.

A premium bundle may combine cosmetic items into a clearly described package.

Maintain a fair free progression path with desirable unlocks. Premium items may look exclusive, but must not be the only route to functional equipment or core gameplay.

## Explicit prohibitions

Do not implement:

- Purchases that directly determine task success.
- Paid exclusive functional upgrades.
- Paid increases to random reward probabilities.
- Paid loot boxes or other paid randomized reward mechanics.
- Deliberately miserable cooldowns intended to force spending.
- Fake purchase buttons.
- Fake game-pass ownership.
- Invented product IDs.
- Client-authoritative purchase rewards.

Cosmetic items and convenience features should be implemented so they can be connected to real Game Passes or Developer Products later.

Keep monetization disabled until valid IDs are supplied. Clearly identify the configuration values that the developer must replace.

Validate purchase receipts on the server when Developer Products are implemented. Never trust a client message that claims a purchase succeeded.

# 8. ROBLOX TECHNICAL ARCHITECTURE

Before modifying anything, inspect the existing workspace and discover which tools, project files, assets, and development conventions are already present.

Do not delete an existing project or replace existing functionality without understanding it.

If the project uses Rojo, follow its existing configuration and directory structure. If not, create a coherent, maintainable Roblox project and explain how to import or place the scripts in Roblox Studio.

Use idiomatic Luau and separate responsibilities into small modules.

A reasonable architecture includes:

- `ReplicatedStorage/Shared/Config`
- `ReplicatedStorage/Shared/TaskDefinitions`
- `ReplicatedStorage/Shared/EventDefinitions`
- `ReplicatedStorage/Remotes`
- `ServerScriptService/Services/ShiftService`
- `ServerScriptService/Services/TaskService`
- `ServerScriptService/Services/MalfunctionService`
- `ServerScriptService/Services/ProgressionService`
- `ServerScriptService/Services/DataService`
- `ServerScriptService/Services/MonetizationService`
- `StarterPlayer/StarterPlayerScripts/ClientController`
- `StarterPlayer/StarterPlayerScripts/UIController`
- `StarterGui` for organized interface components.

Adapt this structure if the existing repository has a better established architecture. Do not create unnecessary abstractions just to make the file tree look sophisticated.

## Server authority and security

All important gameplay state must be controlled by the server.

The server must validate:

- Whether a task is active.
- Whether an interaction is permitted.
- Whether a player is sufficiently close to an interaction.
- Whether an item can be picked up, moved, or inserted.
- Whether an event is currently active.
- Whether a reward has already been granted.
- Whether a purchase receipt is valid.

Validate RemoteEvent and RemoteFunction arguments, enforce reasonable rate limits, and prevent duplicate task completions.

Never accept a client-supplied currency amount, arbitrary reward value, arbitrary player target, or unrestricted change to machine stability.

The client may request an action. The server determines whether it succeeds.

## Persistence

Use DataStoreService for persistent progression.

Save only the data needed to restore a player's progression, such as currency, level, unlocked items, owned cosmetics, and collection progress.

Requirements:

- Safe default profiles.
- Protected DataStore calls with appropriate error handling.
- UpdateAsync where appropriate for safe updates.
- Periodic autosaving.
- Saving when a player leaves.
- BindToClose handling.
- No unbounded retry loops.
- Graceful behavior if saving is unavailable in Studio or if a DataStore request fails.
- No saving of transient shift state that should be reset between sessions.

Do not claim persistent saving has been verified if the experience has not been published with DataStore access enabled and tested.

## Performance

Use efficient event-driven logic where possible.

Avoid creating unbounded Heartbeat connections, unnecessary per-frame scans, duplicated event timers, and large numbers of loose physics objects.

Use anchored objects for static structures. Apply constraints and physics only where they materially improve gameplay.

Clean up temporary instances, disconnect unused connections, and ensure that repeated shifts do not accumulate obsolete objects.

# 9. IMPLEMENT THE MVP FIRST

Build the following complete vertical slice before expanding the feature set:

1. A polished machine hall.
2. A working shift lifecycle.
3. Machine stability and a visible timer.
4. At least six functional task types.
5. At least five malfunction events.
6. A playable solo mode and support for multiplayer.
7. Server-validated interactions and rewards.
8. A working currency and basic upgrade or cosmetic unlock system.
9. Basic persistent player progression.
10. A usable shop interface, with monetization disabled until real IDs are configured.
11. A complete success/failure sequence and shift reset.
12. A concise onboarding flow.
13. A configuration system that makes future content additions straightforward.

Do not add a giant open world, player trading, complicated crafting, competitive ranked modes, or numerous additional currencies in the MVP.

Do not start dozens of speculative features before the core loop works.

# 10. REQUIRED DEVELOPMENT WORKFLOW

## Stage A: Inspect

Inspect the workspace, tooling, project structure, and dependencies.

Identify what is already working, what is missing, and which testing tools are available. Check the proposed title for obvious collisions if browsing is available.

Do not mistake lack of internet access for proof that a name or mechanic is original.

## Stage B: Establish the implementation plan

Write a brief, concrete plan with the intended files, core systems, and acceptance criteria.

Then continue into implementation. Do not stop after producing the plan.

## Stage C: Build

Implement the complete MVP, including scripts, environment, interfaces, configuration, persistence, and the initial gameplay content.

Ensure that files actually exist in the workspace and that required instances can be created or loaded correctly.

Reuse existing code where sensible.

## Stage D: Test and repair

Run all appropriate tests available in the environment, including static checks and Luau analysis tools where installed.

Inspect for:

- Syntax and type errors.
- Broken module paths.
- Missing required objects.
- Invalid RemoteEvent interactions.
- Race conditions in shift and event transitions.
- Duplicate rewards.
- Players becoming stuck in a task.
- Malfunctions that fail to terminate.
- Objects or connections leaking after each shift.
- UI elements that fail to update.
- Save failures that corrupt or reset progression.
- Purchases that incorrectly grant items.
- Mobile interaction problems.

Fix the issues you find. Repeat this process after meaningful changes rather than simply reporting the issues and leaving them untouched.

Do not falsely claim that a live Roblox multiplayer session has been tested if only static checks were possible.

## Stage E: Final verification

Provide a short, actionable manual test plan for Roblox Studio, including how to test:

- One player completing multiple shifts.
- Two or more players completing simultaneous tasks.
- A shift ending successfully.
- A shift ending in meltdown.
- Event termination and object restoration.
- Player departure and rejoining.
- Persistence when DataStore access is enabled.
- Invalid or excessive remote requests.
- Desktop and mobile UI behavior.
- The disabled state of monetization before real product IDs are supplied.

If you can run Roblox Studio or a compatible simulation environment, use it. Otherwise, explicitly identify what remains untested.

# 11. ACCEPTANCE CRITERIA

The MVP is not complete merely because scripts have been written.

The implementation should satisfy the following criteria:

- A player can join and understand the objective quickly.
- The machine begins issuing tasks without an unnecessarily long wait.
- At least six task types can be completed.
- Malfunction events begin, replicate, terminate, and restore the environment correctly.
- The machine can fail and recover without permanently destroying player progress.
- Multiple players can interact without duplicate rewards or broken shared state.
- One player can play independently.
- Currency is earned through valid server-side actions.
- Persistent progression is implemented with appropriate failure handling.
- Monetization cannot be exploited or accidentally grant unconfigured products.
- The primary interface is functional and readable on small screens.
- The visual design feels coherent, intentional, and original.
- Temporary objects and event connections are cleaned up.
- The project has clear instructions for opening, running, and testing it.
- No unsupported claim of successful testing is included in the final report.

If some criteria cannot be verified because of limitations in the available environment, state that clearly and provide the exact next step needed to verify them.

# 12. FINAL DELIVERABLES

When you finish, provide:

1. The actual implemented project files in the current workspace.
2. A concise directory tree of the important files.
3. Instructions for opening and running the project in Roblox Studio.
4. A summary of the implemented gameplay systems.
5. A list of tests executed and their actual results.
6. A list of remaining limitations or unverified behaviors.
7. The exact configuration values that must be supplied before publishing or enabling monetization.
8. A prioritized roadmap for future updates based on retention and player feedback.

Do not provide an enormous theoretical design document in place of implementation.

Do not rewrite working code just to make it look different.

Do not leave placeholder features disguised as completed functionality.

Do not claim that the game is flawless, viral, or fully tested without evidence.

Your priority is to deliver the smallest genuinely playable, polished, secure, and extensible version of **SHIFT ZERO: KEEP IT RUNNING**, then improve it through specific, verifiable iterations.

Start by inspecting the current workspace and proceed through implementation, testing, and repair until you have completed every part that the available environment allows.