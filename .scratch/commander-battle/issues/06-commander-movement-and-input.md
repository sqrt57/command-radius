# How does the player control commander travel and react to danger?

Map: [Find the design for a commander-positioning battle](../map.md)
Labels: wayfinder:grilling
Type: grilling
Status: resolved
Blocked by: 04, 05

## Question

Prerequisites: [What pressures constrain commander repositioning?](04-commander-pressure.md) and [How do terrain and obstacles create tactical positioning choices?](05-terrain-and-obstacles.md).

What minimal movement and input rules let the player reposition a vulnerable commander, escape predictable enemies, and choose when to stop and build influence?

The agreed foundation is clicking a destination and traveling there while the battle continues. Decide how new destinations replace existing ones, whether the player can stop travel immediately, what happens when a destination is unreachable or lies in impassable terrain, and how routes around obstacles are selected and communicated. Resolve whether any pause control is compatible with the agreed continuous real-time battle.

Describe the intended relationship between commander and soldier travel speeds so baiting and disengagement are possible without making danger trivial; leave exact numerical speed for tuning. Test redirecting midway through enemy-held ground, stopping short of a fight to build influence, and escaping damage long enough to begin healing.

Specify observable controls and behavior, not a pathfinding implementation or the full interface presentation.

## Comments

### Agreed movement and input rules

The user agreed to all five proposed rules:

- A new valid destination immediately replaces the current destination. A dedicated Stop control halts the commander at their current position so stationary influence can begin building. There is no movement queue for the first prototype.
- A destination inside a barrier or otherwise unreachable is rejected with visible feedback. The commander's previous movement continues; an invalid command does not implicitly stop or redirect them.
- The commander automatically follows the shortest traversable route around barriers, with the planned route visible. Routing does not avoid enemies automatically; the player can guide a safer journey by issuing intermediate destinations.
- The commander travels modestly faster than soldiers, allowing timely disengagement while crossing enemy-held ground can still cause damage. There is no sprint or dash. Exact speed and survivability remain for tuning.
- Battle decisions and movement commands happen in real time. A pause suspends play, and no orders are accepted while paused.

The user subsequently confirmed the complete consolidated ruleset.

## Answer

The player controls commander travel with a single active destination. A new valid destination immediately replaces the current one, including during travel through enemy-held ground. A dedicated Stop control halts the commander immediately at their current position so stationary influence can begin building. The first prototype has no movement queue.

Clicks inside barriers or at otherwise unreachable destinations are rejected with visible feedback. An invalid command preserves the existing movement, or leaves a stationary commander stationary; it does not implicitly stop travel or substitute another destination.

The commander automatically follows the shortest traversable route around barriers, and the planned route is visible. Routing does not automatically avoid enemies. The player can guide a safer journey by issuing intermediate destinations, each replacing the current destination rather than joining a queue. This preserves responsibility for judging whether a detour or crossing is safe.

The commander travels modestly faster than soldiers. Prompt retreat should allow disengagement from predictable enemies and an opportunity to reach the damage-free delay required for healing, while crossing enemy-held ground can still cause damage. There is no sprint or dash. Exact speeds, health, and survivability remain for tuning.

Battle decisions and movement commands happen in continuous real time. A pause suspends play, with no orders accepted while paused; it provides a break rather than a tactical order-entry mode.

The user confirmed the complete ruleset. These rules cover redirecting midway through danger, stopping short of a fight to build influence, and escaping to recover. Exact input bindings and broader interface presentation remain for presentation design; pathfinding implementation is outside this decision.
