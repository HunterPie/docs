---
layout: post
title: "Monster Widget"
date: 2022-02-13 19:03 -0300
badge: docs
math: true
categories: [Documentation, Overlay, Widgets]
---
The Monster Widget is responsible to track and display all the big monsters information. It is one of the most complex widgets and each single component is designed to be simple without losing information.

## Widget Structure

![monster-widget-structure](/Static/widgets/monster-widget.png)

### Monster Parts

Parts are represented by the blue, yellow and red bars under the ailments component. Their visual representation depends on what type of part it is:

Color | Represents | Description
:----:|:----------:|--------------------
<ion-icon name="water" style="fill:#22aae1;"/> | `Flinch` | Flinch values represent when the monster is going to flinch or get staggered.
<ion-icon name="water" style="fill:#fdc45b;"/> | `Break`  | Break values represent when a part is about to break.
<ion-icon name="water" style="fill:#e53737;"/> | `Sever` | Severable parts are the ones that can be cut off from a monster.
<ion-icon name="water" style="fill:#7f7f7f;"/> | `Broken` | A part will become Grey when it's either broken or severed. 
<ion-icon name="water" style="fill:#EE4B96;"/> | `Qurio`* | A part will become Pink when it's related to the monster's Qurio state. 

When a part has all three values, the priority order is **always** `Qurio` > `Sever` > `Break` > `Flinch` and the exact values displayed under the part health bar will follow that priority.

> By default, HunterPie only shows monster's parts when you have the monster as a target. Read [Targeting a monster](#targeting-a-monster) for more information.
{: .prompt-info }

> A Qurio part is exclusive for **Monster Hunter Rise: Sunbreak**
{: .prompt-note }

### Monster Ailments

Ailments are statuses and debuffs you can inflict on a monster, HunterPie supports all of them, however, some of them might display as `Unknown` since ailments are mapped manually and require testing.

They're designed to be as simple to read as possible, displaying Build Up, Duration and also how many times that Ailment has been activated on that monster. Each ailment has its own individual color to make it easier to know what ailment has been inflicted without having to read its name.

> By default, HunterPie only shows monster's ailments when you have the monster as a target. Read [Targeting a monster](#targeting-a-monster) for more information.
{: .prompt-info }

### Targeting a monster

Having to target a monster to see its information is part of HunterPie's design to avoid cluttering the screen with multiple monsters information, HunterPie offers a couple ways to target monsters:

- **Lock-on:** Uses the game lock-on/targeting system. This is better if you want to have 100% control over HunterPie's monster target.
- **Inference:** HunterPie will calculate a score based on distance, health and how recent was the last damage the monster took. This option is good if you don't want to manually target anything, however, since it's based on guessing, it *can* target the wrong monster in certain conditions.
- **Map Pin:** This options uses the map pin mechanic from Monster Hunter World to target the monster.
- **Quest Target:** This option only exists for Monster Hunter Rise and will use the quest's monster as the target.

### Capture indicator

For capturable monsters, an upside down triangle (<ion-icon name="caret-down-sharp" style="fill:#FBB623"></ion-icon>) will be placed on the exact percentage where the monster will become capturable.

### Orientation

Monster Widget supports two orientations, `Vertical` and `Horizontal`


Orientation | Description
:----------:|:--------------------
Vertical    | Monster health bars will be placed on top of each other in the order they spawn
Horizontal  | Monster health bars will be placed side by side in the order they spawn
