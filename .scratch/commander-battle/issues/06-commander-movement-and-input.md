# How does the player control commander travel and react to danger?

Map: [Find the design for a commander-positioning battle](../map.md)
Labels: wayfinder:grilling
Type: grilling
Status: open
Blocked by: 04, 05

## Question

Prerequisites: [What pressures constrain commander repositioning?](04-commander-pressure.md) and [How do terrain and obstacles create tactical positioning choices?](05-terrain-and-obstacles.md).

What minimal movement and input rules let the player reposition a vulnerable commander, escape predictable enemies, and choose when to stop and build influence?

The agreed foundation is clicking a destination and traveling there while the battle continues. Decide how new destinations replace existing ones, whether the player can stop travel immediately, what happens when a destination is unreachable or lies in impassable terrain, and how routes around obstacles are selected and communicated. Resolve whether any pause control is compatible with the agreed continuous real-time battle.

Describe the intended relationship between commander and soldier travel speeds so baiting and disengagement are possible without making danger trivial; leave exact numerical speed for tuning. Test redirecting midway through enemy-held ground, stopping short of a fight to build influence, and escaping damage long enough to begin healing.

Specify observable controls and behavior, not a pathfinding implementation or the full interface presentation.
