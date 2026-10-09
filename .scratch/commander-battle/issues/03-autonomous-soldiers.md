# How do autonomous soldiers make commander influence matter?

Map: [Find the design for a commander-positioning battle](../map.md)
Labels: wayfinder:grilling
Type: grilling
Status: resolved
Blocked by: 01, 02

## Question

Prerequisites: [What makes commander influence worth relocating for?](01-commander-influence.md) and [What is the player trying to achieve in one battle?](02-battle-objective.md).

What minimal movement and combat behavior should friendly and enemy soldiers have so the battle advances on its own and commander positioning can change its course?

Define what soldiers do without commander support and how they respond to the selected influence. Decide how soldiers choose destinations or targets and whether allies and enemies share baseline rules. Test what happens when the commander leaves a group, arrives mid-fight, or potentially draws soldiers away from a useful position.

Specify observable behavior rather than an AI implementation or a roster of troop types.

## Comments

### Agreed baseline and open defense behavior

- Soldiers automatically advance toward the opposing base, engage nearby enemies, and resume advancing after defeating them; this needs an additional rule for base defense.
- The initial battle uses one soldier type with short-range melee combat.
- Both sides receive automatic reinforcements in small groups at regular intervals, allowing recovery after losing current soldiers. Exact quantities and timing remain for tuning.
- Reinforcement points are distinct from the bases being defended. Their number and behavior remain to be decided.
- The user proposed simple overall attack/defend controls as a possible way to provide base defense; this is not yet a settled control rule.

### Agreed battle stances and reinforcement-point rules

- The player has one army-wide Attack / Defend toggle. Attack advances toward the enemy base; Defend returns soldiers toward the player base to guard its surrounding area. Soldiers still choose their own movements and targets.
- During Attack, soldiers near their own base automatically intercept enemies threatening it; distant soldiers continue attacking unless the stance changes.
- Each side has one fixed reinforcement point, distinct from its base, that cannot be captured or destroyed and produces soldiers until the battle ends. Placement remains for battlefield design.
- The enemy uses the same stances, automatically switching to Defend when its base is threatened and returning to Attack when the threat clears. Threat boundaries and switching behavior remain to be specified.

## Answer

The first battle uses one soldier type with short-range melee combat. Friendly and enemy soldiers share the same baseline movement, targeting, and combat rules. Soldiers select the nearest eligible opponent and retain that target until it dies or leaves engagement range. Once a fight ends, they resume their stance's destination. Commander influence increases friendly damage without changing movement intent or target selection; entering or leaving its radius changes the bonus immediately under the agreed influence rules.

The player controls one army-wide Attack / Defend battle stance, rather than issuing direct movement orders or selecting individual soldiers:

- **Attack:** advance toward the opposing base, engaging nearby opponents along the way and occupying its capture area when able.
- **Defend:** return toward the army's own base, gather around it, and intercept opponents inside its defense area. Return to guard after threats are gone.

A stance change updates destinations immediately for soldiers not fighting. Soldiers already fighting finish their current nearby fight before following the new destination; the toggle does not force disengagement. Reinforcements follow the current stance. Local base-defense pursuit remains bounded as described below, including during a stance change.

Each base has a visible defense area larger than its capture area. Local defense takes precedence over advancing: soldiers currently inside their own defense area intercept opponents entering it even during Attack, while distant soldiers continue advancing. Defenders stop pursuing opponents that leave the defense area and return to their stance's destination. This boundary prevents a retreating opponent from drawing defenders away indefinitely.

The enemy begins in Attack. An opposing soldier entering its base's defense area triggers army-wide Defend. It returns to Attack after the area has remained clear for a short interval, avoiding rapid switching at the boundary. The commander alone does not trigger this response. Commander vulnerability and personal combat remain a separate decision.

Each side has one fixed reinforcement point, physically distinct from the base it defends. Reinforcement points cannot be captured or destroyed and automatically produce small groups at regular intervals until the battle ends. Both sides use the same baseline reinforcement rules. Losing all current soldiers therefore permits recovery rather than independently ending the battle.

The intended positioning choices are to support an advancing fight, strengthen the local base defense, or travel between them while the soldiers continue acting autonomously. Leaving a group removes its influence benefit without redirecting it; arriving mid-fight changes its damage support without changing its target. The stance toggle changes overall intent, while commander position concentrates combat support.

Exact engagement ranges, defense-area sizes, reinforcement quantities and intervals, the enemy's clear interval, and combat statistics remain for tuning. Reinforcement-point placement, battlefield routes, and obstacle effects remain for terrain and encounter design.
