# Commander Tactics

A small-scale tactics game centered on influencing an autonomous battle through commander positioning.

## Language

**Commander**:
The player-controlled entity whose position is the player's main means of influencing a battle.
_Avoid_: Player entity

**Soldier**:
An autonomous combatant that participates in the battle rather than receiving direct movement orders from the player.

**Commander influence**:
The increase in damage dealt by friendly soldiers within the commander's influence radius. Its strength belongs to the commander, remains active during travel, and builds while stationary.

**Influence radius**:
The fixed distance around the commander that defines which friendly soldiers receive commander influence.

**Player base**:
The location friendly soldiers must defend from capture; enemy capture of it loses the battle.

**Enemy base**:
The location friendly soldiers must capture while the player base remains uncaptured to win the battle.

**Reinforcement point**:
A location where new soldiers enter the battle, distinct from the base their side must defend.

**Battle stance**:
The army-wide intent that guides autonomous soldiers: Attack advances toward the opposing base, while Defend returns to guard their own base. Soldiers choose their own movement and combat targets within that intent.

**Defense area**:
The visibly marked area around a base where soldiers respond to threats against that base. It is larger than the capture area and bounds defenders' pursuit.

**Capture**:
Taking an opposing base through continuous occupation of its area by attacking soldiers without defending soldiers contesting it. An interruption resets capture progress.
