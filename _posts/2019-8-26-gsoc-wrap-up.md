---
layout: post
title: "GSoC Wrap Up!"
---
Today marks the final day of my GSoC journey! I had always wished to participate in this prestigious program but could never enter the world of OpenSource, until I stumbled upon The Terasology Foundation! I love games and coding, how about combining them both?! Terasology is a voxel-based sandbox game with various gameplay modes and extensible through lots of modules. My project was to extend the Light and Shadow gameplay module and complete a basic Capture-The-Flag mode with many other features!

The journey was a full rollercoaster ride with many ups and downs. At times I found myself immersed for hours to ultimately find the bug with a one line solution! I learnt a lot about the Entity-Component-System architechture, the 'multi-faceted' World Generation along with skills like maintaining code quality, documenting, testing and debugging.

# Features Added

## Gameplay features

A lot of basic gameplay features were added to take the Gameplay Arc of my project to completion. Check my PRs to know more! I also had to deal with certain other problems like correction of the mesh of players and game UI which weren’t originally the part of the planned project.

**Game Over screen with Statistics:**
![Game Over screen with Statistics](/images/gsoc-wrap-up/stats.png)

## Towers
Towers were perhaps the most time-consuming part of my project. We discussed several implementations and studied other modules like MultiBlock, StructureTemplates before deciding to go forward with the current implementation. Currently, Towers exist as a single block which can be placed wherever you want. Then you have to interact with it to get to activate it. 

**Rook based Tower:**
![Rook based Tower](/images/gsoc-wrap-up/tower.png)

**What is left?**
Towers need to be made modular so that they can be used with the other module ‘GooeyDefence’.

## Markets
Markets module was created by me to add a barter system based buying. Barter System was chosen so that we can have players mine for certain resources to buy the items instead of just resources. It also helps us implement an upgrading system where a more powerful weapon can be bought only in exchange for some other weapon. One needs to add `Purchasable Component` to an item to add it to Market.

**Market Screen:** (Pardon the icon size)
![Market Screen](/images/gsoc-wrap-up/market.png)


**What is left?**
The current state of this module is such that buy is implemented to work in exchange for a single item. The multi-item and block removal system has been implemented and awaiting merge. Once it gets merged, Basic Market would be complete.

## Minimap
Minimap module was currently supported only for a single user. I extended the functionality for Multiplayer mode and also added support for custom icons instead of the arrow.

**Spades and Hearts showing different team players on Minimap:**
![Spades and Hearts showing different team players on Minimap](/images/gsoc-wrap-up/minimap.png)

## Weapons
I extended the basic staff based weapon in CombatSystem module, combined with some AlterationEffects and gave it LightAndShadow Twist. The weapons are based on the Classic Card Game Symbols.

- **Hearts Staff:** Attracts the enemy towards you
- **Spades Staff:** Repels the enemy away from you
- **Diamonds Staff:** Stuns the enemy
- **Clubs Staff:** Adds Poison damage to the enemy

**The LaS Weapons!:** (Thank You Tejas ‘majordwarf’ Tank for the custom textures :D)
![The LaS Weapons!](/images/gsoc-wrap-up/weapons.png)

## World Generation
World generation was the most different feature I came across during this project. The concepts were very different and this wiki was very helpful to understand them. I implement a small arena with surrounding regions raised. I also tried to add a small ying-yang pedestal at the center. 

**LaS Game Arena:**
![LaS Game Arena](/images/gsoc-wrap-up/world.png)

# Contribution Summary
## LightAndShadow:

- Health HUD reskinning based on team [#79](https://github.com/Terasology/LightAndShadow/pull/79)
- Changing player skins through skeletal mesh [#80](https://github.com/Terasology/LightAndShadow/pull/80)
- Respawn and heal player on death [#82](https://github.com/Terasology/LightAndShadow/pull/82)
- Handle inventory on death [#83](https://github.com/Terasology/LightAndShadow/pull/83)
- Added Statistics and Game Restart Systems [#88](https://github.com/Terasology/LightAndShadow/pull/88)
- Destroy dropped items on death after a delay[#89](https://github.com/Terasology/LightAndShadow/pull/89) (Closed due to #93)
- Health hud fix for reconnects and restarts [#90](https://github.com/Terasology/LightAndShadow/pull/90)
- Game Restart Implementation [#91](https://github.com/Terasology/LightAndShadow/pull/91)
- Player Statistics Implementation [#92](https://github.com/Terasology/LightAndShadow/pull/92)
- Teleport flag after delay on drop [#93](https://github.com/Terasology/LightAndShadow/pull/89)
- Clear game over screen on close [#95](https://github.com/Terasology/LightAndShadow/pull/95)
- Teleport Held Flags on Restart [#96](https://github.com/Terasology/LightAndShadow/pull/96)
- Restart permission [#97](https://github.com/Terasology/LightAndShadow/pull/97)
- Halt sun on game start [#100](https://github.com/Terasology/LightAndShadow/pull/100)
- LAS Global Entity Implementation [#101](https://github.com/Terasology/LightAndShadow/pull/101)
- Remove statistics wigdet in deathscreen when it is closed [#103](https://github.com/Terasology/LightAndShadow/pull/103)
- Integrate minimap with LASTeam based icons [#104](https://github.com/Terasology/LightAndShadow/pull/104)
- Implement LightAndShadow Capture-The-Flag World! [#105](https://github.com/Terasology/LightAndShadow/pull/105)  

## Engine:

- Fix for Incorrect VisualCharacter entity [#3686](https://github.com/MovingBlocks/Terasology/pull/3686)
- Fix getText() function in UIText [#3689](https://github.com/MovingBlocks/Terasology/pull/3689)
- VisualCharacterSystemTest Fix and Whitelist PermissionManager [#3695](https://github.com/MovingBlocks/Terasology/pull/3695)

## Other Modules

- Basic Implementation for Towers [#1](https://github.com/Terasology/Towers/pull/1)
- Basic Implementation for Market [#1](https://github.com/Terasology/Market/pull/1)
- Add remove command [#1](https://github.com/Terasology/Inventory/pull/1)
- Implement multiplayer support for minimap [#10](https://github.com/Terasology/Minimap/pull/10)
- Add support for custom icons for players [#12](https://github.com/Terasology/Minimap/pull/12)
- Added hearts and spades icons for minimap [#31](https://github.com/Terasology/LightAndShadowResources/pull/31)
- Added custom staff textures [#32](https://github.com/Terasology/LightAndShadowResources/pull/32)
- Add LaS Themed Weapons! [#33](https://github.com/Terasology/LightAndShadowResources/pull/33)
- Add Alteration effects and Impulse based weapons support [#43](https://github.com/Terasology/CombatSystem/pull/43)

# Future Plans and Ideas

Live statistics screen can be added instead of online players overlay. Currently, the statistics are only shown at the game over screen.
Team balance
Entities loading incorrectly when loading a saved game.

# Relevant Links
- Proposal:&nbsp;[LightAndShadowRemastered](https://docs.google.com/document/d/1oCJkH3_xWyyEUc85LJE6sklgDZvNIcZU2DI0OT5pz98/edit?usp=sharing) 
- Github:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Project #17](https://github.com/orgs/Terasology/projects/17)
- Forum:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Weekly Updates](https://forum.terasology.org/threads/gsoc-2019-light-and-shadow-remastered.2266/)
- Discord:&nbsp;&nbsp;&nbsp;#light-and-shadow at Terasology’s [discord server](http://discord.gg/Terasology)

## Repositories

- [Engine](https://github.com/MovingBlocks/Terasology)
- [LightAndShadow](https://github.com/Terasology/LightAndShadow)
- [LightAndShadowResources](https://github.com/Terasology/LightAndShadowResources)
- [Towers](https://github.com/Terasology/Towers)
- [Market](https://github.com/Terasology/Market)
- [Minimap](https://github.com/Terasology/Minimap)
- [CombatSystem](https://github.com/Terasology/CombatSystem)
- [AlterationEffects](https://github.com/Terasology/AlterationEffects)

# Acknowledgements

I would like to thank The Terasology Foundation and Google for providing me with this wonderful opportunity to work and contribute to Open Source. I would like to thank my mentors Tobias ‘skaldarnar’ Nett, Nihal ‘nihal111’ Singh, Iaron ‘iaronaraujo’ Araujo for their support and guidance throughout the summers. I would also like to thank Rasmus ‘cervator’ Praestholm, Quinn ‘jellysnake’ Roberts and all others who are a part of this wonderful community, for helping me whenever needed and getting acquainted with the codebase.

It has been a summer full of learning and there’s more, right? I would like to learn more about Terasology’s Behavior and Rendering systems in future. I would love to keep contributing to Terasology and help others coming to this organisation :D

 
