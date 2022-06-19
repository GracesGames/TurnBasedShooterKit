---
Layout: page
title: Features
permalink: /features/
---

# Features

***

The Turn Based Shooter Kit provides:

__Shared components__

* _Dialog Component_: Allows any actor (e.g. terminals, NPCs) to have dialog lines
* _Stats Component_: Define stats and their influence on damage dealt and taken, for example: accuracy, defense and agility
* _Health Component_: Defines the actor's health and armor stats. Handles health regeneration and death state

__Player__

* Grid based movement and rotation
* Weapon selection and fire requests
* Object interaction
* _Experience Component_: Defines player experience and level
* _Interaction Component_: Allows the player to interaction with terminals, NPCs, doors etcetera
* _Inventory Component_: Handles the player items and weapons. Defines types, amounts and max amounts
* _Item Component_: Allows the player to use items
* _Vision Component_: Defines the player's current vision (what is in front of the player)

__Weapon system__

* Each weapon is easy to set up using the customization options: burst size, weapon range, damage and damage radius, fire delays, accuracy and more
* _AmmoComponent_: Handles the ammo for the weapon. Defines the ammo per shot, ammo type and whether it weapon has unlimited ammo

__Enemies__

* Easily define more enemy by inheriting from the BaseEnemy class and overriding the component values
* _EnemyActivationComponent_: Handles the activation state and defines the activation radius
* _EnemyAttackComponent_: Defines the enemy attack using stats like attack range, attacks per turn, damage and damage radius
* _EnemyMoveComponent_: Defines the enemy moves using stats like move time and moves per turn

__Items__

* Predefined health and armor items as examples
* Generic SimpleItem that can be modified for most use cases (e.g. giving ammo)
* Weapon items to unlock weapons on pick-up

__Objects__

* Interactive objects such as sliding doors, terminals, exits to other levels
* Exploding barrels and level decoration

__Character select__

* Allow the player to choose their archetype
* Selection of 3 archetypes available

__Save load system__

* Save and load any time during the game
* Keeps track of player, enemy and object status using component data
* Easily extendible
* Saves the data per level

__HUD__

* Current health / Maximum health
* Current armor / Maximum armor
* Health and armor packs
* Current turn
* Vision of the player
* Log of the recent events
* Game over
    * Game over text
    * Load game option
    * Return to main menu

__Menus__

* Pause menu
    * Continue
    * Inventory
    * Save and load game
    * Quit
* Main menu
    * Start
    * Player archetype selection
    * Controls
    * Quit
    
__Other__

* Example animations (Flipbooks)
* Example SFX
* Example game music

Fully customizable to support the needs of your game