# What makes commander influence worth relocating for?

Map: [Find the design for a commander-positioning battle](../map.md)
Labels: wayfinder:grilling
Type: grilling
Status: resolved
Blocked by: none

## Question

What influence mechanic makes commander placement a meaningful choice, with reasons both to stay and to relocate?

Explore bonuses, attracting soldiers, or a deliberately small combination. Decide whether influence exists while moving, whether a stationary effect grows over time, and what happens to accumulated effect when movement begins. These are user-proposed possibilities, not commitments.

Describe who or what is affected and how proximity matters. Test the design with concrete situations: supporting a losing flank, staying in an already useful position, and moving between threatened areas. Establish why neither permanent camping nor constant movement should be the obvious answer.

Resolve the behavioral rule and intended trade-off; leave numerical tuning for later.

## Comments

### Agreed influence foundations

- Influence provides a local combat bonus to friendly soldiers without attracting them or directing their movement.
- A fixed, visibly marked radius determines eligibility; soldiers outside it receive no benefit.
- Baseline influence remains active during travel. Stationary influence builds gradually to a cap; beginning movement immediately resets it to baseline.
- The specific combat bonus and remaining behavioral boundaries are still under discussion.

## Answer

Commander influence increases the damage dealt by friendly soldiers within a fixed, visibly marked radius. It does not attract soldiers or direct their movement, and it changes no other combat attribute.

Baseline influence is active during commander travel. While the commander remains stationary, its strength gradually builds to a cap. Beginning movement immediately resets that strength to baseline.

The buildup belongs to the commander, not to individual soldiers. A friendly soldier entering the radius immediately receives the current bonus; leaving immediately removes it. There is no lingering benefit or separate soldier buildup.

The intended trade-off is stronger support at the current position versus immediate baseline support where it is more urgent. Supporting a losing flank can justify sacrificing accumulated strength; staying is useful while the current fight still needs support. After a fight is won, another threatened area can become the better position. Staying may be correct in a particular situation; there is no influence decay or mandatory relocation timer. Constant movement sacrifices the stationary bonus.

The user also confirmed that terrain and obstacles introduce additional tactical urgencies. Their concrete effects are a separate decision, not an assumed influence rule.

Exact radius, damage bonus, buildup rate, and cap remain for later tuning. Whether terrain affects influence across obstacles remains to be decided with the terrain rules.
