---
layout: post
title: "Damage Meter Widget"
date: 2022-06-14 23:21 -0300
badge: docs
categories: [Documentation, Overlay, Widgets]
---
The Damage Meter Widget is responsible for tracking and displaying yours and your party members damage and damage per second, as well as plotting everything in a graph for better understanding of your hunts.

## UI Design

![damage-meter-widget](/Static/widgets/damage-meter-widget-v2.png) *Damage Meter Widget*

## Damage Accuracy

### Monster Hunter Wilds

For Monster Hunter Wilds, the damage is tracked in two different ways:

1. If the player is in a quest, the quest award damage value will be used. This value is synchronized with every party member, which means it is the most accurate value possible and everyone in the party will receive the actual damage each party member dealt. The limitation is that it:
    - Only works in normal quests, arena quests do not count.
    - The value will be updated only once every 5 seconds for remote players and in real time for the local player.
2. As a fallback, if there is no accurate damage value available, the not-as-accurate value will be used. This value is always calculated by your game regardless if you're the host or not, and since it is not synced amongst party members, the value can have some inconsistencies when comparing to the meter of other players.

In both cases, your own damage is always accurate.

> **Warning:** Only damage coming directly from weapons are accounted for, this is how the game handle these damage calculations. HunterPie **DOES NOT** calculate anything, it just displays the values that your game calculates.
{:.prompt-warning}

### Monster Hunter World

The damage for World is calculated by the game itself, it is the same damage that is used in the quest awards screen (after finishing the quest). Since this is a value synced with every player in the party, the damage for each player will be the same regardless if you're the host or not.

In the case of expeditions, guiding lands and missions that have no target (Kulve Taroth Siege), the damage is **not** tracked by the game, HunterPie will use its fallback implementation. The fallback can only track the local player's damage, this is a **game limitation**.

### Monster Hunter Rise

To calculate the damage for Monster Hunter Rise, HunterPie will sum every hit damage and assign it to whoever did the damage. This does not consider:

- Environmental damage
- Damage done by ailments (e.g: poison, blast)
- Damage done by other monsters

> **Warning:** Hitting a dead monster will still count as damage done to a monster. This is a known issue and will be fixed eventually.
{:.prompt-danger}

## Settings

### Player colors

You can change yours and your party members color by going to the settings tab and clicking on the color configuration.

### Damage plot

#### Moving Average DPS

HunterPie will display the moving average DPS by default, the moving average is more useful than the overall DPS plotting because the overall DPS tends to stabilize in the long run.

![moving-average-dps-vs-dps](/Static/client/moving-avg-dps-vs-dps.png) *moving average DPS vs Overall DPS*

It is highly recommended to use the moving average, however it is also possible to toggle it off and plot either overall DPS or total damage.

> **Note:** Changing the plot mode while in a hunt will not update the previous points that were already plotted in the graph.
{: .prompt-warning }

### DPS Calculation

By default, HunterPie will calculate the damage per second based on the quest timer, however, this can be inaccurate especially when joining in-progress quests (such as SOSes), you can change the DPS calculation strategy in the Damage Meter settings.

Strategy | Description
---------|--------------------------
Relative to quest | The quest timer will be used to calculate players DPS
Relative to join | The time when each player joined the quest will be subtracted <br> from the quest timer when calculating players DPS
Relative to first hit | The time when each player hit a monster for the first time <br> will be subtracted from the quest timer when calculating players DPS

