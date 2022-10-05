# Team 1

## Canonical game repo URL:

https://github.com/Zogren01/team1_game

## Team Members
* Advanced Topic Subteam 1: Physics

	* Brian Sostek
		* Pitt Username: bes140
		* Github Username: briansostek
	* Bailey Mathien
		* Pitt Username: blm135
		* Github Username: blm135
	* Jacob Salmon
		* Pitt Username: jhs59
		* Github Username: jakesalmon

* Advanced Topic Subteam 2: Enemy AI

	* Zach Ogren
		* Pitt Username: zpo1
		* Github Username: Zogren01
	* Jack Baker
		* Pitt Username: jmb446
		* Github Username: jbaker013
	* Giovanni Versace
		* Pitt Username: giv8
		* Github Username: GioVersace
	* Ethan Zhao
		* Pitt Username: etz2
		* Github Username: Ethanzhaocs


## Game Description

A horror themed metroid style game, in which the player has a time limit for each attempt before being reset. The player can purchase and find several abilities to help them progress through the game in the time available. They will need to navigate through different rooms and face various advanced enemies in order to find an reach the ending. 

The screen size for the game will be 1280x720.

Items the player will have available:
* double jump ability
* projectile attack
* vanishing move (temporarily invisible to enemies)
* extra time
* extra health
* extra damage

## Advanced Topic Description

### ADVTOPIC1 -- Physics

The physics of the game world will function like a 2D simulation of the real world. The game will feature accurate rigid body colllisions between movable objects. There will be breakable objects found in the game world that will further showcase the use of these simulated collisions.
    
### ADVTOPIC2 -- Enemy AI

The game will consist of at least 3 different enemy types, that all have distinctly different behavior and are capable of coordinating with one another as well as obstacles on the map.

The enemies line of sight will be computed by Bresenham’s line scan algorithm. This will allow them to identify things like cover, other enemies, and map hazards as nodes on a map. In addition to this, they will be able to see the health values of themselves and anything in their line of sight. This means the enemies will not be able to simply access map data, but will have to understand what is accessible to them in real time.

Then, based on thier own stats, what type of enemy they are, and what information they understand about their surroundings, they will be able to make decisions about what their desired position should be.

The enemies will patrol a set area or where the player was last seen until they identify the players location or the location of another enemy that they are designed to interact with.
Enemies will pathfind using the A* algorithm to reach their desired goal, which will require an understanding of how to navigate through the map while bound by the same physics as the player character.

This will result in a set of enemies that are essentially finite state machines, that act in a way that appears to be intelligent and can interact with their surroundings, the player, and other enemies in real time.

This design for enemies will allow for flexible behavioral patterns for the enemies throughout development, but the current planned enemies will have the following behavioral patterns:
	1. Melee enemy:
		* prioritizes damaging the player with varying levels of aggression based on their own health
		* will attempt to damage player with surrounding obstacles if possible
		* prioritize taking the player somemplace dangerous while retreating if possible
		* if it encounters a ranged enemy, it will ignore its health and continually attempt to keep itself between the player and the ranged enemy
	2. Ranged enemy:
		* prioritizes keeping the maximum distance between itself and the player that is within the range of its attack
		* if it encounters a melee enemy, it will attempt to keep itself within this enemies line of sight while attacking the player
		* if it's health is low enough, it will search for a health enemy
	3. Health enemy:
		* this enemy will run for cover on sight of the player
		* this behavior will be overwritten if it encounters an enemy that does not have full health, in which case it will try to heal this enemy using its melee attack
		* will make a dash towards the player if the player is at low enough health

## Midterm Goals

* The basic layout of map will have been created, along with some of the rooms the player can explore
* The player is able to move through this world and use attacks
* Game timer will be functioning, and reset the player when it runs out
* Item store will be set up (no items needed yet)
* At least one type of enemy AI will exist and be able to challenge the player

## Final Goals

* 15%: Rigid body collisions
* 10%: Breakable objects
* 35%: at least 3 distinct enemy types with advanced movement and decisionmaking
* 20%: at least 3 unique items created and accessible to the player to change their abilities and gameplay (not including extra time/health/damage)
* 10%: Reaching MVP

## Stretch Goals

* 5%: Stretch goal 1 -- boss battle
* 5%: Stretch goal 2 -- jetpack item available and additional level in the game 
	* the base game will be one level, with at least 6 large rooms for the player to explore
	* each room will be at least twice as big as the screen display of 1280x720
	* the additional level will consist of at least 2 new rooms, that require the player to maneuver with the new jetpack mechanic to explore
