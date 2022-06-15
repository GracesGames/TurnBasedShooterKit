---
Layout: page
title: Documentation
permalink: /documentation/
---

# Documentation

***

### Components

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

