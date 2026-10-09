# Find the design for a commander-positioning battle

Labels: wayfinder:map

## Destination

Reach a prototype-ready design for one small, playable battle in which the player influences autonomous soldiers primarily through commander positioning. Resolve enough about movement, influence, soldier behavior, and battle outcomes to build and evaluate the core loop.

## Notes

- This effort is design planning; implementation follows after the map is resolved.
- Agreed framing: single-player against an autonomous enemy force; continuous real-time battle, including during commander travel; no direct soldier movement orders.
- The player clicks a destination and the commander travels there at a speed to be determined.
- Terrain and obstacles are part of the battle and should introduce tactical urgencies; their concrete rules remain to be decided.
- Consult `grilling` and `domain-modeling` for decision conversations. Consult `prototype` when a decision needs a concrete artifact for human feedback.
- Domain vocabulary lives in [the glossary](../../GLOSSARY.md).
- Child tickets live in `issues/`; dependencies use `Blocked by`. The frontier consists of open tickets whose dependencies are resolved, in filename-number order.
- Charting agreements are recorded here as framing. Future ticket resolutions live in their tickets, with only a gist and link below.

## Decisions so far

- [What makes commander influence worth relocating for?](issues/01-commander-influence.md): Local damage support builds while stationary and resets to baseline on movement; changing tactical needs motivate relocation.
- [What is the player trying to achieve in one battle?](issues/02-battle-objective.md): Capture the single enemy base while preventing capture of the player base, using symmetric occupation rules; target roughly 10 minutes without a deadline.
- [How do autonomous soldiers make commander influence matter?](issues/03-autonomous-soldiers.md): Autonomous melee soldiers follow army-wide Attack / Defend stances, protect bounded defense areas, and receive recurring reinforcements from separate, invulnerable points.
- [What pressures constrain commander repositioning?](issues/04-commander-pressure.md): A vulnerable, support-only commander can bait predictable enemies and heal after a damage-free delay; commander death loses the battle, and terrain constrains travel.
- [How do terrain and obstacles create tactical positioning choices?](issues/05-terrain-and-obstacles.md): Impassable barriers create chokepoints and detours, block melee reach, and allow commander influence through them.
- [How does the player control commander travel and react to danger?](issues/06-commander-movement-and-input.md): Immediate redirect and Stop, visible shortest traversable routes, rejected invalid destinations, a modest speed advantage over soldiers, and pause without order entry.
- [What battlefield layout creates competing demands on commander position?](issues/07-battlefield-layout.md): Mirrored two-route battlefield, alternating reinforcement routes, rear reinforcement points, and a shared central cross-passage; separated fights require commander relocation.
- [What encounter scale keeps both routes active and commander choices readable?](issues/08-encounter-scale-and-forces.md): Six starting soldiers per side, three-soldier reinforcements every 20 seconds alternating routes, meaningful commander travel times, and small local fights without an initial population cap.
- [What must the player see to make informed commander-positioning decisions?](issues/09-battle-readability.md): Fixed whole-battle view, visible influence recipients and buildup, health and recovery feedback, base boundaries and capture states, stance and home-threat indicators, and explicit movement, Stop, and pause controls.
- [What initial tuning makes commander relocation consequential and recoverable?](issues/10-initial-battle-tuning.md): Virtual-meter combat, influence, movement, recovery, and capture baselines make relocation consequential; timely saves require friendly defenders, with explicit tuning diagnostics.
- [What representative encounter and observations will test the commander-positioning core loop?](issues/11-representative-encounter-evaluation.md): Three comparable normal-battle play styles, targeted starts for missing coverage, player explanations, and provisional evidence-based verdicts test positioning, recovery, readability, and pacing.
- [What presentation and technical medium will make the battle prototype easy to build and evaluate?](issues/12-prototype-presentation-and-medium.md): Desktop Chromium prototype using TypeScript, SVG, and HTML, with separate simulation, repeatable starts, configuration-based tuning, read-only state inspection, and Markdown evaluation summaries.

## Not yet specified

No remaining fog or open decision tickets. The prototype-ready design destination is reached; the map is complete and ready for implementation handoff.

## Out of scope

- Building the playable prototype during this planning effort.
- Campaigns, progression, multiplayer, and production content or polish: beyond the one-battle design destination.
