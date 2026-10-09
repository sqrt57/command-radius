# What must the player see to make informed commander-positioning decisions?

Map: [Find the design for a commander-positioning battle](../map.md)
Labels: wayfinder:grilling
Type: grilling
Status: resolved
Blocked by: 08

## Question

Prerequisites: [What battlefield layout creates competing demands on commander position?](07-battlefield-layout.md) and [What encounter scale keeps both routes active and commander choices readable?](08-encounter-scale-and-forces.md).

What minimum visual feedback and controls make the selected battle mechanics understandable at the chosen encounter scale?

Decide how the player reads commander influence range and stationary strength, commander health and recovery, soldier allegiance and intent, current battle stance, base capture and defense areas, capture progress, and threats on the other route. Include the already-agreed visible commander route, rejected-destination feedback, Stop, and pause without order entry.

Make the shared cross-passage and impassable barriers legible. Test noticing a home-base threat while supporting an advance, recognizing which soldiers receive influence through a barrier, and understanding why local defenders stop pursuing. Specify the information and interactions needed for the prototype, leaving visual polish and technical medium for later.

## Comments

### Agreed minimum feedback and controls

The user agreed to all six recommendations:

- Keep the entire battlefield visible on one fixed screen: both routes, both bases, reinforcement points, barriers, and the central cross-passage. Clearly distinguish walkable ground from barriers.
- Continuously show the commander's influence radius, mark friendly soldiers currently receiving its bonus (including across barriers), and display the current damage bonus and stationary buildup. Movement visibly resets buildup to baseline.
- Keep commander health prominent and distinguish waiting for the damage-free recovery delay from active healing. Give soldiers small health bars and distinguish allegiance through both color and shape. Movement and attack animations convey activity; omit individual target lines and intent labels initially.
- Permanently show distinct capture and defense boundaries at both bases. Show valid capture progress, explicit contested feedback, and visible progress reset when occupation is interrupted. Defense boundaries explain why defenders stop pursuing opponents outside them.
- Show the player's selected Attack / Defend stance and the enemy's current stance in a compact status strip. Keep a home-threat warning visible while enemy soldiers occupy the player base's defense area, increasing its emphasis during active capture.
- Use click-to-move with visible destination and route markers, plus labeled Stop, Attack / Defend, and Pause controls. Provide S for Stop and Space for pause/resume. Briefly flash rejected destinations while preserving the previous order. Display a clear pause overlay and disable movement, Stop, and stance orders while paused.

The user subsequently confirmed the complete consolidated ruleset.

## Answer

The prototype uses one fixed view of the entire battlefield. Both routes, both bases, reinforcement points, barriers, and the central cross-passage remain visible. Walkable ground and impassable barriers are clearly distinguishable, allowing the player to monitor the other route while supporting a local fight.

The commander's influence radius is continuously visible. Friendly soldiers currently receiving influence carry a simple marker, including those within range across barriers. A compact indicator displays the current damage bonus and stationary buildup; movement visibly resets buildup to baseline. This communicates actual recipients rather than suggesting barriers block influence.

Commander health remains prominent. Recovery feedback distinguishes waiting for the damage-free delay from active healing. Soldiers have small health bars, and allegiance is distinguished through both color and shape. Movement and attack animations communicate activity; individual target lines and intent labels are omitted initially.

Both bases permanently display visually distinct capture and defense boundaries. Valid occupation shows capture progress; defending soldiers contesting capture produce explicit contested feedback. Interrupted occupation visibly resets progress under the existing capture rules. The defense boundary also communicates where local defenders stop pursuing, without adding a separate pursuit display.

A compact status strip shows the player's selected Attack / Defend stance and the enemy's current stance. A persistent home-threat warning appears while enemy soldiers occupy the player base's defense area, with increased emphasis during active capture. Together with the whole-battle view, this makes a home threat noticeable while the commander supports an advance elsewhere.

Controls consist of click-to-move, visible destination and planned-route markers, and labeled Stop, Attack / Defend, and Pause controls. S invokes Stop; Space pauses or resumes. A rejected destination flashes briefly without replacing the previous order. A clear pause overlay appears while paused, and movement, Stop, and stance orders are disabled until play resumes.

The user confirmed this complete ruleset. It specifies the minimum information and interactions for the prototype; visual polish and technical medium remain for later planning.
