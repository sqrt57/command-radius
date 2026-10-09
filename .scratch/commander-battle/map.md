# Find the design for a commander-positioning battle

Labels: wayfinder:map

## Destination

Reach a prototype-ready design for one small, playable battle in which the player influences autonomous soldiers primarily through commander positioning. Resolve enough about movement, influence, soldier behavior, and battle outcomes to build and evaluate the core loop.

## Notes

- This effort is design planning; implementation follows after the map is resolved.
- Agreed framing: single-player against an autonomous enemy force; continuous real-time battle, including during commander travel; no direct soldier movement orders.
- The player clicks a destination and the commander travels there at a speed to be determined.
- Influence is deliberately undecided. Candidate effects include bonuses and attracting soldiers. Stationary influence may strengthen over time; movement may also produce an effect. None of these candidates is yet a chosen mechanic.
- Other design areas remain open; there are no additional user-imposed constraints yet.
- Consult `grilling` and `domain-modeling` for decision conversations. Consult `prototype` when a decision needs a concrete artifact for human feedback.
- Domain vocabulary lives in [the glossary](../../GLOSSARY.md).
- Child tickets live in `issues/`; dependencies use `Blocked by`. The frontier consists of open tickets whose dependencies are resolved, in filename-number order.
- Charting agreements are recorded here as framing. Future ticket resolutions live in their tickets, with only a gist and link below.

## Decisions so far

<!-- Append links and one-line gists as decision tickets are resolved. -->

## Not yet specified

- Battlefield geometry, force composition, and encounter scale: shape these around the selected influence and battle objective.
- The concrete movement and input model, including travel speed, destination changes, obstructions, and whether a pause is useful.
- How the player reads commander influence, soldier intentions, and battle progress; clarity needs depend on the selected mechanics.
- Parameters and tuning: discover which quantities matter, and how to make positioning choices noticeable without predetermining a best strategy.
- The smallest representative encounter and the observations that would show whether commander positioning is fun.
- Prototype presentation and technical medium, once the behavior to test is clear.

## Out of scope

- Building the playable prototype during this planning effort.
- Campaigns, progression, multiplayer, and production content or polish: beyond the one-battle design destination.
