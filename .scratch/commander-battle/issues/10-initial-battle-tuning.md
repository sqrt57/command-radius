# What initial tuning makes commander relocation consequential and recoverable?

Map: [Find the design for a commander-positioning battle](../map.md)
Labels: wayfinder:grilling
Type: grilling
Status: resolved
Blocked by: 08

## Comments

### Agreed initial combat, distance units, and enemy clear interval

- Soldiers start with 100 health and deal 10 damage once per second, without armor or damage randomness. An unsupported one-on-one fight lasts roughly 10 seconds once attacks begin.
- Measure battlefield distances in virtual meters and movement speeds in meters per second. The previously proposed body-diameter measurements were not accepted; numerical ranges remain under discussion.
- The enemy returns to Attack after its defense area remains free of opposing soldiers for 5 continuous seconds. Another opposing soldier entering restarts the countdown; the commander alone does not trigger army-wide Defend.

### Agreed movement, influence, survival, and capture baseline

- Soldier speed: 3 m/s. Commander speed: 4 m/s. Melee reach: 1 m beyond body contact. Influence radius: 6 m.
- Commander travel targets imply traversable paths of 32–48 m between route fights and 60–80 m from midfield to home. Usual route fights must remain impossible to support simultaneously.
- Influence starts at +25% soldier damage and builds linearly to +100% over 10 stationary seconds. Movement immediately resets it to +25%.
- Commander health: 150. Healing starts after 5 damage-free seconds at 5 health per second; taking damage restarts the delay.
- Uncontested base capture takes 25 continuous seconds, independent of the number of attacking occupants. Existing contest and reset rules apply.
- The user agreed to all four recommendations. Remaining discussion covers engagement distance, base-area dimensions, stress tests, and tuning observations.

### Agreed engagement, base geometry, and evaluation boundaries

- Soldiers acquire opponents within 6 m, retain and pursue them until they die or move more than 8 m away, and attack only within melee reach. Base defenders still stop pursuit at their defense-area boundary.
- Each base has a 4 m capture radius and a 16 m defense radius, both visibly marked. Both routes enter the defense area; the central cross-passage remains outside it.
- Leaving a fight for 8–12 seconds can cost that fight. Returning to a threatened base is viable only when friendly soldiers can contest capture; commander arrival alone cannot interrupt it. Recoverability does not guarantee recovery from every late response or lost fight.
- Expose all agreed combat, movement, influence, healing, capture, area, and reinforcement values for tuning.
- If camping dominates, inspect route pressure and influence strength. If relocation rarely helps, inspect travel time, combat duration, and buildup time. If prompt home responses consistently fail, inspect capture time and defender arrival times. If exposure is trivial or instantly fatal, inspect commander health, pursuit distance, and healing.
- Keep the uncapped starting model. Repeated local fights exceeding roughly 8 soldiers per side are a signal to investigate accumulation, especially during prolonged Defend. Inspect reinforcement cadence and combat throughput first; consider a population cap if needed. Diagnostic prompts do not automatically change balance.
- The user agreed to all four recommendations and subsequently confirmed the complete tuning decision.

## Question

Prerequisite: [What encounter scale keeps both routes active and commander choices readable?](08-encounter-scale-and-forces.md).

For the agreed starting forces, reinforcement cadence, local fight sizes, and commander travel-time targets, what initial parameter values or explicit relationships make commander relocation consequential without making timely recovery impossible?

Choose an adjustable starting baseline for soldier combat duration and engagement range, commander influence radius and damage bonus buildup, commander speed and survivability, healing delay, base capture duration and defense-area size, and the enemy's clear interval before returning to Attack. Preserve the resolved mechanics; distinguish concrete initial values from relationships that depend on the eventual prototype's units.

Stress-test leaving a supported fight for 8–12 seconds, returning from midfield to a threatened base in 15–20 seconds, escaping enemies to heal, and soldier accumulation during prolonged Defend. Identify which parameters should be exposed for tuning and what observations would justify adjusting them. The roughly ten-minute battle remains a target to evaluate rather than a promised outcome.

## Answer

The user confirmed this adjustable prototype starting baseline. Battlefield distances use virtual meters and speeds use meters per second.

| Parameter | Starting value |
| --- | --- |
| Soldier health | 100 |
| Soldier damage and attack interval | 10 damage once per second; no armor or damage randomness |
| Soldier movement speed | 3 m/s |
| Target acquisition distance | 6 m |
| Target disengagement distance | More than 8 m; retain the target until then or its death |
| Melee reach | 1 m beyond body contact |
| Commander health | 150 |
| Commander movement speed | 4 m/s |
| Commander healing | 5 health/s after 5 damage-free seconds; damage restarts the delay |
| Influence radius | 6 m |
| Influence damage bonus | +25% baseline, rising linearly to +100% over 10 stationary seconds; movement immediately resets it to baseline |
| Base capture radius | 4 m |
| Base defense radius | 16 m |
| Base capture duration | 25 continuous uncontested seconds, independent of attacker count |
| Enemy return-to-Attack delay | 5 continuous seconds without opposing soldiers in its defense area; entry restarts the countdown |

Existing mechanics remain in force: barriers block travel and melee but not influence; defenders stop pursuit at their defense-area boundary; the commander cannot capture or contest a base and alone does not trigger enemy army-wide Defend. Both base areas are visibly marked, both routes enter the defense area, and the central cross-passage remains outside both defense areas.

The previously resolved encounter retains six starting soldiers per side, three reinforcements every 20 seconds alternating routes, and initially no population cap. Usual route fights cannot receive influence from one stationary commander simultaneously.

### Travel relationships and recovery stress tests

- **Change routes:** 8–12 seconds at 4 m/s implies a traversable path of 32–48 m between usual route fights. Leaving for that duration can cost a fight: unsupported one-on-one combat lasts roughly 10 seconds, versus roughly 8 seconds at baseline influence or 5 seconds at maximum influence. These are comparative estimates, not guarantees for group fights or discrete attack timing.
- **Return home:** 15–20 seconds implies a traversable path of 60–80 m from midfield to home. If capture starts as the commander departs, only 5–10 seconds remain on arrival. Friendly soldiers must reach the capture area to contest; commander arrival alone cannot save it, and Defend does not force disengagement from current fights. Recoverability means timely decisions can save some situations, not every late response.
- **Warning at home:** direct inward travel from the 16 m defense boundary to the 4 m capture boundary takes roughly 4 seconds at soldier speed when unobstructed. This creates warning and interception space before capture starts.
- **Escape and heal:** the commander has a 1 m/s speed advantage over soldiers, allowing escape on an unobstructed route. Terrain and multiple attackers can still make crossing hostile ground dangerous. At continuous nominal damage, survival is roughly 15 seconds against one attacker or 5 seconds against three. Recovery from near death takes roughly 30 seconds of healing plus the 5-second delay; further damage restarts that delay.
- **Prolonged Defend:** keep the uncapped initial model and inspect accumulation. Repeated local fights above roughly 8 soldiers per side are a diagnostic signal rather than an automatic cap trigger.

### Tuning controls and observations

Expose the agreed combat, movement, engagement, influence, healing, capture, base-area, and reinforcement values for adjustment. Preserve behavioral rules unless a later decision explicitly reopens them.

- If camping dominates, inspect route pressure and influence strength.
- If relocation rarely helps, inspect travel time, combat duration, and buildup time.
- If prompt home responses consistently fail, inspect capture time and defender arrival times.
- If commander exposure is trivial or instantly fatal, inspect health, pursuit distance, and healing.
- If prolonged Defend produces unreadable crowds, inspect reinforcement cadence and combat throughput first; consider a population cap if necessary.

These observations guide investigation rather than automatically changing balance. A roughly ten-minute battle remains a target to evaluate, not a promised result. The next decision defines a representative encounter evaluation and the observations needed to judge the core loop.
