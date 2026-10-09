# What pressures constrain commander repositioning?

Map: [Find the design for a commander-positioning battle](../map.md)
Labels: wayfinder:grilling
Type: grilling
Status: resolved
Blocked by: 01, 02

## Question

Prerequisites: [What makes commander influence worth relocating for?](01-commander-influence.md) and [What is the player trying to achieve in one battle?](02-battle-objective.md).

Given the selected influence and objective, what costs or risks make choosing where to send the commander consequential?

Determine whether travel time and the loss or change of influence already provide enough pressure. Decide whether the commander can be attacked, obstructed, or defeated, whether the commander participates in combat, and what consequences apply if relevant. Evaluate a journey through an enemy-held area and a choice between two places needing support.

Favor the smallest coherent ruleset; vulnerability and personal combat are open questions, not assumed requirements. Exact movement controls and parameter tuning can be specified after these pressures are understood.

## Comments

### Agreed commander exposure, combat role, and passage

- The commander is vulnerable. How enemies attack the commander and what happens when the commander is defeated remain to be decided.
- The commander contributes exclusively through influence, with no personal attacks or ability to block enemy soldiers. The commander alone cannot stop base capture.
- The commander obeys impassable terrain but can pass through friendly and enemy soldiers without being physically blocked. Concrete terrain rules remain for the terrain decision.

### Agreed targeting and defeat consequence

- The commander has health and is a normal melee target under the existing soldier targeting rules: nearest eligible opponent, retained until it dies or leaves engagement range, without special commander priority.
- The user wants predictable soldier behavior that player skill can slightly exploit, citing creeps in DOTA / League of Legends as a reference. This is a behavioral reference, not adoption of those games' full targeting rules.
- Commander health reaching zero immediately loses the battle, adding a defeat condition alongside capture of the player base.
- Health recovery and the interaction between commander targeting and bounded base defense remain to be confirmed.

### Agreed recovery and bounded defense

- The commander slowly heals after taking no damage for some time, rather than carrying all damage permanently through the battle. Exact delay and healing rate remain for tuning.
- Enemy soldiers guarding their base can target the commander inside their defense area under normal targeting rules, but stop pursuing when the commander leaves that area.
- The commander alone does not trigger the enemy's army-wide Defend stance; this preserves the earlier stance decision while allowing local baiting.

## Answer

Repositioning trades accumulated stationary influence for baseline support at a new location. Travel takes time while the battle continues, so choosing between two threatened fights also means leaving one without commander support during the journey.

The commander is vulnerable, has health, and is a normal melee target under the existing soldier targeting rules. Soldiers select the nearest eligible opponent and retain that target until it dies or leaves engagement range; there is no special commander priority. An enemy already fighting a soldier does not switch simply because the commander approaches. Predictable behavior that skilled play can slightly exploit is intentional: the commander can bait unengaged enemies and move away to break engagement. The user's DOTA / League of Legends creep comparison is a behavioral reference, not adoption of those games' full rules.

After a damage-free delay, the commander slowly regenerates health up to full health. Taking damage interrupts healing and restarts the delay. Commander health reaching zero immediately loses the battle, adding a defeat condition alongside capture of the player base. This extends the outcome rules recorded in [What is the player trying to achieve in one battle?](02-battle-objective.md).

The commander contributes exclusively through influence: no personal attacks, physical blocking of soldiers, base capture, or contesting capture. The commander obeys impassable terrain but can pass through soldiers from either side. Crossing enemy-held ground therefore risks damage or death without soldier bodies physically preventing passage; barriers can force detours.

Enemy soldiers guarding their base can engage the commander inside their defense area under normal targeting rules, but stop pursuing when the commander leaves that area. The commander alone does not trigger the enemy's army-wide Defend stance. This allows local baiting without drawing base defenders arbitrarily far away and preserves the bounded-defense rule from [How do autonomous soldiers make commander influence matter?](03-autonomous-soldiers.md).

The user confirmed this complete ruleset, including damage restarting the healing delay. Exact commander health, healing delay and rate, and travel speed remain for tuning. Concrete terrain effects and movement controls remain separate decisions.
