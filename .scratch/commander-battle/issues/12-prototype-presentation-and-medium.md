# What presentation and technical medium will make the battle prototype easy to build and evaluate?

Map: [Find the design for a commander-positioning battle](../map.md)
Labels: wayfinder:grilling
Type: grilling
Status: resolved
Blocked by: 09, 10, 11

## Question

Which presentation and technical medium should the future one-battle playable prototype use to deliver the agreed whole-battle view, controls, adjustable tuning, and repeatable evaluation runs with minimal build effort?

Choose the target device and input assumptions, runtime and delivery method, and rough visual presentation sufficient to distinguish soldiers, the commander, barriers, influence, base areas, and battle feedback. Determine how tuning values and repeatable normal or targeted starts should be accessible, and how the lightweight evaluation observations will be recorded. Identify any technical constraints that affect feasibility of the agreed design or require further investigation before implementation can begin.

Keep this decision at prototype-ready fidelity: choose enough to guide implementation and evaluation without production polish. Building the playable prototype remains beyond this planning map.

Prerequisites:
- [What must the player see to make informed commander-positioning decisions?](09-battle-readability.md)
- [What initial tuning makes commander relocation consequential and recoverable?](10-initial-battle-tuning.md)
- [What representative encounter and observations will test the commander-positioning core loop?](11-representative-encounter-evaluation.md)

## Comments

### Target device and input agreed

The user agreed to target desktop or laptop with mouse and keyboard, keeping the whole battlefield visible in one landscape view. Controls retain click-to-move, labeled action buttons, S for Stop, and Space for pause.

Runtime and delivery remain undecided. The user asked to compare alternatives, including whether HTML improves LLM observation and whether a browser game engine adds value.

### Runtime, presentation, and observation approach agreed

After comparing HTML/SVG, Canvas, a browser game engine, and Godot, the user agreed to:

- A locally served browser application using TypeScript, an SVG battlefield, and HTML controls. Keep simulation separate from rendering and expose a small read-only simulation-state snapshot for automated inspection. SVG provides inspectable battlefield entities; screenshots remain necessary to evaluate visual readability. Rendering performance during prolonged Defend remains something to verify in the future prototype.
- A simple top-down diagrammatic presentation: flat ground and barriers, soldiers distinguished by team color and shape, a distinct commander symbol, small health bars, differentiated influence/capture/defense boundaries, and simple movement and attack feedback.
- Manual evaluation records in a reusable Markdown run sheet, supported by diagnostics showing elapsed battle time, outcome, and soldier counts by side and route. Record player explanations, key relocations, danger recognition, and provisional verdicts.

Tuning access, repeatable starts, and the precise scope of inspection support remain to be settled.

### Tuning, repeatability, inspection, and delivery agreed

The user agreed to all four follow-up recommendations:

- Keep tuning in one clearly named configuration file and display active values in a collapsible diagnostics panel. Change tuning between runs, restart from the same initial conditions, and include active configuration in exported run metadata.
- Provide a pre-run setup panel for the normal battle and targeted scenarios added only when normal play leaves required evaluation coverage missing. Starts use explicit repeatable initial states and selected tuning; Restart repeats the selected start from time zero. Record a seed if randomness is used.
- Expose a read-only state snapshot including simulation time, tuning and start identifiers, soldier and commander positions and health, influence strength and recipients, stances, and base capture state. Provide Copy run summary to produce Markdown metadata and current diagnostics for the run sheet. Player explanations and observations remain manual; full replay recording is not needed initially.
- Target a current desktop Chromium browser with a documented local development command. Fit the battlefield to the available window while preserving proportions and verify readability at a typical 1280 × 720 viewport. Resizing affects presentation only, not virtual-meter distances or simulation behavior.

All questions raised for this ticket now have agreed answers. Consolidated confirmation is pending before resolution.

### Consolidated confirmation

The user confirmed the complete consolidated approach. No further planning questions were identified for this ticket.

## Answer

The future one-battle prototype is a locally served browser application targeting a current desktop Chromium browser on a desktop or laptop with mouse and keyboard. Provide a documented local development command. Preserve the agreed click-to-move controls, labeled action buttons, S for Stop, and Space for pause, including the existing prohibition on orders while paused.

Use TypeScript with the simulation separate from rendering, an SVG battlefield, and ordinary HTML controls. SVG exposes inspectable battlefield entities; a read-only simulation-state snapshot supports precise automated observation, while screenshots and human feedback assess visual readability. A browser game engine is not required for the initial prototype. Verify SVG performance under prolonged Defend accumulation in the future prototype; keeping simulation separate allows a rendering change if needed.

### Presentation and sizing

Use a simple top-down diagrammatic style with flat ground and barriers, soldiers distinguished by team color and shape, a distinct commander symbol, small health bars, differentiated influence/capture/defense boundaries, and simple movement and attack feedback. Preserve all feedback specified in [What must the player see to make informed commander-positioning decisions?](09-battle-readability.md).

Keep the entire battlefield visible in one landscape view. Fit it to the available window while preserving proportions and verify readability at a typical 1280 × 720 viewport. Resizing changes presentation only, never virtual-meter distances or simulation behavior.

### Tuning and repeatable starts

Keep tuning in one clearly named configuration file and show active values in a collapsible diagnostics panel. Change tuning between runs, then restart from the same initial conditions. Include the active configuration in exported run metadata.

Provide a pre-run setup panel for the normal battle and targeted scenarios added only when normal play leaves required evaluation coverage missing. Each start uses an explicit repeatable initial state and selected tuning. Restart repeats the selected start from time zero. If randomness is needed, use and record a seed. Preserve the comparison and coverage rules in [What representative encounter and observations will test the commander-positioning core loop?](11-representative-encounter-evaluation.md).

### Inspection and evaluation records

Expose a small read-only state snapshot containing simulation time, tuning and start identifiers, soldier and commander positions and health, influence strength and recipients, stances, and base capture state.

Show elapsed battle time, outcome, and soldier counts by side and route in diagnostics. Provide Copy run summary to produce Markdown metadata, active configuration, and current diagnostics for a reusable Markdown run sheet. Record player explanations, important relocations, danger recognition, and provisional verdicts manually. Full replay recording is not required initially.

The user confirmed this complete approach. No additional planning investigation is required before implementation; rendering performance and visual readability are checks for the future playable prototype. Building and evaluating that prototype remain beyond this map's planning destination.
