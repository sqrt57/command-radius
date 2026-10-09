# What is the player trying to achieve in one battle?

Map: [Find the design for a commander-positioning battle](../map.md)
Labels: wayfinder:grilling
Type: grilling
Status: resolved
Blocked by: none

## Question

What objective and win/loss conditions give the player a readable purpose in one small real-time battle against an autonomous enemy?

Choose the battle's objective, how success and failure occur, and the intended pacing or approximate duration. Consider how the objective can create competing demands on commander position. Keep the decision at the one-battle level rather than expanding into campaign or progression systems.

## Comments

### Agreed objective and duration

- The player's base must stay alive while the player captures the enemy base or bases.
- One battle should last around 10 minutes.
- Capture rules, the number of enemy bases, and precise outcome conditions remain under discussion.

### Agreed base rules and pacing

- The first battle has one enemy base.
- Friendly soldiers capture it by holding its area for a short period without enemy soldiers contesting it.
- The player's base has health and is lost when enemies destroy it.
- Victory requires capturing the enemy base while the player's base survives.
- Around 10 minutes is a pacing target, not a hard deadline; outcomes come from the bases rather than the clock.
- Capture interruption and simultaneous outcome boundaries remain under discussion.

### Final confirmation and correction

- The user agreed that interrupted capture resets progress, that outcomes are immediate, and that simultaneous captures favor defeat.
- The player base is captured using the same occupation mechanics as the enemy base. Neither base has health; this supersedes the earlier health-and-destruction proposal.

## Answer

The first battle has one player base and one enemy base. The player wins by capturing the enemy base while keeping the player base uncaptured. Enemies win by capturing the player base. Neither base has health or is destroyed through damage.

Both bases use the same capture mechanics: soldiers of the attacking side must continuously occupy the base's capture area for a short period, with no defending soldiers in that area. Capture progress resets when defending soldiers enter the area or when all attacking soldiers leave or die. The commander alone cannot capture a base or preserve capture progress.

Capturing the enemy base immediately wins the battle; enemies capturing the player base immediately loses it. If both bases are captured simultaneously, defeat takes priority. Losing all friendly soldiers is not a separate defeat condition; whether recovery is possible depends on the later soldier-behavior decision.

A typical battle should last around 10 minutes. This is a pacing target, not a hard deadline. The battle ends through base capture rather than a timer.

The objective creates competing demands on commander position: support friendly soldiers clearing and holding the enemy base, or support soldiers preventing capture at home. Commander influence helps soldiers defeat opponents; it does not itself capture bases.

Exact capture duration, capture-area size, and other numerical tuning remain for later decisions.
