# What battlefield layout creates competing demands on commander position?

Map: [Find the design for a commander-positioning battle](../map.md)
Labels: wayfinder:grilling
Type: grilling
Status: resolved
Blocked by: 05, 06

## Question

Prerequisites: [How do terrain and obstacles create tactical positioning choices?](05-terrain-and-obstacles.md) and [How does the player control commander travel and react to danger?](06-commander-movement-and-input.md).

What minimal battlefield layout makes supporting an advance, defending the player base, and repositioning between fights meaningfully compete?

Choose the arrangement of the two bases, their separate reinforcement points, barriers, openings, and connected travel routes. Decide whether one main route or multiple routes are needed, and whether the layout should be symmetric. Account for soldiers' autonomous Attack / Defend behavior rather than assuming direct movement orders.

Test a commander supporting soldiers across a barrier, returning from an offensive fight to a threatened player base, and baiting local defenders without drawing them beyond their defense area. Ensure both bases and reinforcement points have usable travel connections. Leave exact distances, force quantities, and numerical tuning for later.

## Comments

### Agreed battlefield shape

- The user agreed to mirrored terrain, base placement, and reinforcement-point placement for the two sides.
- The user agreed to two connected routes around one central barrier, with openings at either end, keeping the battlefield small and readable.
- Autonomous route use, concrete base and reinforcement placement, and support positions remain to be decided.

### Agreed route use and home areas; shortcut request

- The user agreed that successive reinforcement groups alternate attack routes using the same pattern for both sides. Defend sends soldiers home by the shortest traversable path; nearby combat and local base defense retain priority.
- The user agreed that each base sits in an open home area joining the two routes, with a separate reinforcement point behind it. Reinforcements pass through their home defense area before entering either route.
- The user requested shortcuts for the commander between routes. Whether these are commander-only connections or shared openings, their placement, and the resulting cross-barrier support geometry remain open.

### Agreed shared cross-passage and support coverage

- The user clarified that the shortcut is accessible to commanders and soldiers alike. It runs orthogonally to the usual attack/retreat direction, so soldiers do not usually use it during advance or retreat, but can be lured through it during pursuit.
- The user agreed to one cross-passage halfway along the central barrier, outside both bases' defense areas. Local defenders remain bounded by their defense area.
- The user agreed that the two routes' usual fighting areas are too far apart for one stationary commander to support both at once, while the barrier permits useful support through it near its edges. The cross-passage can temporarily bring soldiers from both routes together.
- These shared openings preserve the existing terrain rule that commander and soldier travel have the same restrictions.

## Answer

The user confirmed the complete ruleset below.

The first battlefield uses mirrored terrain, base placement, and reinforcement-point placement. Two routes run around a central barrier and join in open home areas at either end. Each home area contains its side's base, with a separate reinforcement point behind it, farther from the enemy. Reinforcements pass through their home defense area before entering either route. Both routes connect to both home areas, and both reinforcement points have usable connections to the battlefield.

Successive reinforcement groups alternate attack routes using the same pattern for both sides. Groups use their assigned route when attacking; Defend sends soldiers home by the shortest traversable path. Nearby combat and bounded local base defense retain priority over route intent. Route assignment is autonomous and adds no direct soldier movement orders.

One shared cross-passage lies halfway along the central barrier, outside both bases' defense areas. It runs orthogonally to the usual attack/retreat direction. Commanders and soldiers can both use it: ordinary advances and retreats usually stay on their routes, but soldiers pursuing a target can be lured through the passage. Local defenders still cannot pursue beyond their defense area. The passage is an opening, not an exception to barrier travel restrictions.

The routes' usual fighting areas are separated enough that one stationary commander cannot support both simultaneously. The barrier still permits useful influence support through it near its edges. Soldiers from both routes may temporarily converge at the cross-passage. Relocating through it reduces travel time without removing the choice of which separated fight to support.

The layout supports these positioning scenarios:

- **Support across a barrier:** the commander can strengthen an advancing fight from the opposite side of a barrier. Melee remains blocked across the barrier; enemies can reach the commander through openings.
- **Return to a threatened base:** the commander can use the cross-passage to switch routes, but reaching the home defense area still takes travel time while battle continues.
- **Bait soldiers:** ordinary pursuers can follow through the cross-passage. Base defenders remain bounded by their defense area, preventing indefinite luring away from their base.

Exact distances, force quantities, and numerical tuning remain for later decisions.
