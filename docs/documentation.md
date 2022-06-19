---
Layout: page
title: Documentation
permalink: /documentation/
---

# Documentation

***

### Shared Components

__Dialog Component__

BP_DialogComponent handles the logic for dialog interaction e.g. with a terminal.  
It specifies all possible texts to display and which one to show currently. 
    
__Face Player Component__

BP_FacePlayerComponent handles the rotation of actors that should face the player e.g. enemies, objects, pickups.
By using sprites, this component makes sure each actors is visible to the player.

__Health Component__

BP_HealthComponent handles taking damage, updates health and armor values and a dead state.
It allows for damage modifications based on the actor StatsComponent. 
While it also supports health regeneration, this functionality might not be applicable for a turn based game.

__Stats Component__

BP_StatsComponent is used to define the stats of an actor.
These stats currently support modifying damage dealt and received amounts but can easily be extended for other gameplay purposes.

### Enemies

__Base Enemy__

BP_BaseEnemy is the generic enemy class. It serves as the base class for all enemy types and can be easily customized using the different components and their properties.  
Adding a new enemy is as easy as creating a child actor of the BaseEnemy Blueprint.

__Enemy Activation Component__

BP_EnemyActivationComponent handles the activation state and activation radius for enemies.

__Enemy Attack Component__

BP_EnemyAttackComponent defines the enemy attack using stats like attack range, attacks per turn, damage and damage radius. It also handles the attack animation and attack sound when a flipbook and sound are provided.

__Enemy Move Component__

BP_EnemyMoveComponent defines the enemy moves using stats like move time and moves per turn. 
It first determines the best path to the player using the NavMesh and then checks all four directions of the enemy. It moves in the direction that matches the best with the NavMesh result.

__Enemy Interface__

I_Enemy defines the interface for the Enemy that is used by the save/load system and interaction between the BaseEnemy and its components.

### Game

__Main Menu Game Mode__

BP_MainMenuGameMode is the game mode and specifies the BP_MainMenuPlayerController as default controller. It is used as the game mode in the Main Menu map.

__Turn Based Shooter Game Instance__

BP_TurnBasedShooterGameInstance is the game instance and handles log entries and save and load game logic. It also manages the character archetype selection options. 

__Turn Based Shooter Game Mode__

BP_TurnBasedShooterGameMode is the game mode and handles the current turn.

__Save Game__

BP_GameSaveData, BP_LevelSaveData and any other SaveGame files act as a container for the save data (e.g. current level, health for the HealthComponent).

__Log Interface__

I_Log defines an abstract AddLogEntry function for the GameInstance so every actor can easily add a Log entry.

__Turn System Interface__

I_TurnSystem defines an abstract way to query and progress the current turn.

### Items

__Base Item__

BP_BaseItem is the parent class of all the item types. It handles the activation of the pickup when hitting the player.

__Armor Item__

BP_ArmorItem is an item that adds an armor pack to the player inventory.

__Health Item__

BP_HealthItem is an item that adds a certain amount of health to the player when damaged. Else it will add an Health pack to the player inventory.

__Simple Item__

BP_SimpleItem is a generic item that can be used for any Inventory item (e.g. ammo).

__Weapon Item__

BP_WeaponItem is an item that unlocks a weapon for the player.


### Objects

__BaseObject__

BP_BaseObject is the parent class of all objects. It handles the GetName function for vision (overridden by child Blueprints) and the default components.

__Exit__

BP_Exit is used to travel between levels. It allows to set the player position and rotation in the level, and if not set, the PlayerStart is used.

__Sliding Door__

BP_SlidingDoor is used to travel between rooms. It can require a certain item, for example, key.

__Terminal__

BP_Terminal is used to instruct the player when interacted with. It uses the DialogComponent to define its sentences.

__Barrel__

BP_Barrel is an object that explodes when receiving a certain amount of damage.

__Interactable Interface__

I_InteractableObject defines an abstract way for the player to interact with an object.

### Player

__Player__

BP_Player is the player of the game. It handles player input for movement, rotation, interaction and weapon selection. It also defines what should happen when leveling up.

__Experience Component__

BP_ExperienceComponent defines the current experience and level of the player. It uses a level curve to check how much experience is required per level.

__Interaction Component__

BP_InteractionComponent allows the player to interaction with InteractableObjects.

__Inventory Component__

BP_InventoryComponent is an interactable container for the the player's items and weapons. Defines types, amounts and max amounts and ways to increment and decrement the amounts.

__Item Component__

BP_ItemComponent allows the player to use items via the Pause Menu Inventory.

__Vision Component__

BP_VisionComponent defines the player's current vision (what is in front of the player). It uses the GetName interface call to get the name of the object without casting.

__Player Interface__

I_Player is an abstract way to communicate to the player for the ExperienceComponent and Weapon classes.

### PlayerControllers

__Main Menu Player Controller__

BP_MainMenuPlayerController is responsible for creating and interacting with the Main Menu

__Turn Based Shooter PlayerController__
 
BP_TurnBasedShooterPlayerController is responsible for creating and interacting with the HUD (Pause Menu and HUD changes). It also handles dialog interaction logic and the game over visuals.

__Player Controller Interface__

I_PlayerController is an abstract interface between the game logic (e.g. pause and game over) and the player controller.

### Weapons

__Base Weapon__

BP_BaseWeapon is the parent class of each weapon. It handles the finding of a target and applying damage to it when the player request a burst. The weapon defines multiple properties: burst size, weapon range, damage and damage radius, fire delays, accuracy and more.

__Ammo Component__

BP_AmmoComponent handles the ammo for the weapon. Defines the ammo per shot, ammo type and whether it weapon has unlimited ammo. The current ammo is checked when the player requests a fire.

### UI

All user interfaces support gamepad input. Whether to highlight the selected button can be toggled using the HighlightButtons variable.

__HUD__

BP_HUD is the in-game user interface and shows the player the current health, armor, ammo, turn, vision and log entries.  
It also defines the game over screen with the load game option and option to return to the main menu.  
The pause menu user interface is also integrated in the HUD and allows the player to continue the game, use items in the inventory, save and load the game or return to the main menu.    

__Main Menu__

BP_MainMenu is the main menu user interface and allows the player to start the game, contains the settings like help text and character selection. 

__InventoryItemWidget__

BP_InventoryItemWidget is a visual representation of a inventory item in the HUD pause menu. It shows the amount per item and an button that is enabled when it can be used.