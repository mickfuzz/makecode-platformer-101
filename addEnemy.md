# Remixing a Platformer Game - Add a Static Enemy

## Add a Static Enemy

### Introduction

In this tutorial we will **add a static enemy** to our platformer.
If you want to understand more about how the starting code of the template works then you can follow [this tutorial](https://arcade.makecode.com/beta#tutorial:https://github.com/mickfuzz/makecode-platformer-101)
 to create the game step by step.

#### About this Game Pattern

This game pattern is one of many you can add to your Platformer in this course.

![mechanics space polish and systems](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/patterns/gamemechanic_extralives_800.png)

* **Name:** Add a Static Enemy

* **Description:** Also known as a Hazard, a Static Enemy will kill or damage the health of the player if they touch it. These are often placed in tricky spots which the player is likely to bump into when jumping or trying to collect rewards.  

* **Need for Pattern:** Having hazards increases the challenge of a level, you can place hazards in a way that requires the player to time their jumps well and really control their movement.

* **Related Game Patterns:** Add Moving Enemies [related], Jump on Enemies [related]

* **Coding Concepts involved:** [Loops](learningDimensions#loops), [Events](learningDimensions#events)

* **Links to other Computing Patterns:** , [Change Listener](learningDimensions#change-listener), [Input Event](learningDimensions#input-event)  


## Putting the Pattern into Practice
### We add enemies like we add food.
We add ememies like we add food to the game. Following this tutorial will add static enemies to your game.
Click on the tilemap image for your first level. Create a totally Red tile in **My Tiles**.
Add one or two red blocks to your first level.  

### We add enemies like we add food.
We use a ``||loops:for||`` loop (to save time) that turns all the yellow squares in a tile map into a sprite of kind Food.
Find the following loop in the code.

### We add enemies like we add food.
For first line here reads ``||loops:for element value of array of all...||``
it contains a value and a list. The loop keeps running until it runs out of a values in the list.
This means it will create one item of Food for every yellow block.
Duplicate this code block. Drop the copied loop back into the function after the original one.

![Duplicate loop ](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-add-an-enemy/master/images/duplicate_loop_ae_1.png)

### We add enemies like we add food.

Now change the values of content of this ``||loops:for loop||``. Change the yellow square to a red one.
Change the name of ``||variables:strawberry||`` for the two blocks for it to mentioned. I'll choose ``||variables:snake||`` and change the image too.
Check your code with the example below.

### Create a Collision Listener

We now code what happens when our player overlaps with the enemy ``||variables:snake||``.
Drag in an on player overlap with block from Sprites. Set the second value to be Enemy.
Inside the block drag in from Game block of ``||game:game over||`` and keep it set to **Lose**.

## Test your game and Next Steps

**This tutorial is now complete.**

You can test your game to check that each time you add in a red block in your level tilemaps an enemy appears
and that when you touch the enemy the game ends with a Game Over message.

You can really have a lot of fun with static enemies by putting them in places that make it tricky for your player when
they jump etc. 

When you are done self-testing and playtesting you return to the menu of [Game Patterns](gamePatterns) to choose another to add to your game.

As a next step you may find you want to increase the challenge even more perhaps by adding moving enemies. Or you may find
that you want to balance out the increase of challenge that these hazards have brought and add player lives.
