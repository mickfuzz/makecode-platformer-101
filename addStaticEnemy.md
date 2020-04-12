# Remixing a Platformer Game - Add a Static Enemy

In this tutorial we will **add a static enemy** to our platformer.
If you want to understand more about how the starting code of the template works then you can follow [this tutorial](https://arcade.makecode.com/beta#tutorial:https://github.com/mickfuzz/makecode-platformer-101)
 to create the game step by step.

## About this Game Pattern

This game pattern is one of many you can add to your Platformer in this course.

![mechanics space polish and systems](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/gamemechanic_extralives_800.png)

* **Name:** Add a Static Enemy

* **Description:** Also known as a Hazard, a Static Enemy will kill or damage the health of the player if they touch it. These are often placed in tricky spots which the player is likely to bump into when jumping or trying to collect rewards.  

* **Need for Pattern:** Having hazards increases the challenge of a level, you can place hazards in a way that requires the player to time their jumps well and really control their movement.

* **Related Game Patterns:** Add Moving Enemies [related], Jump on Enemies [related]

* **Coding Concepts involved:** [Loops](learningDimensions#loops), [Events](learningDimensions#events)

* **Links to other Computing Patterns:** , [Change Listener](learningDimensions#change-listener), [Input Event](learningDimensions#input-event)  

## How to implement this Pattern in MakeCode

### We add enemies like we add food.
We add ememies like we add food to the game. Following this tutorial will add static enemies to your game.
Click on the tilemap image for your first level. Create a totally Red tile in **My Tiles**.
Add one or two red blocks to your first level.  

![Add Red Blocks](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/addStaticEnemy.png)


### Looping through the tilemap squares 
For first line here reads **for element value of array of all...**
This line contains a value and a list. The loop keeps running until it runs out of a values in the list.
In this case create one item of Food for every yellow block. 
### Duplicate the Food Loop
Duplicate this loop section. 
![Duplicate loop ](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/duplicate_loop_ae_1.png)
Now we will change the **for loop** will turn the red squares in a tile map into a sprite of kind of Enemy.

### Change the values for our loop to create enemies

Drop the copied loop back into the function after the original one.Change the values of content of this **for loop**. 
Change the yellow square to a red one.Change the name of **food1** for the two blocks for it to mentioned. 
I'll choose to create a new variable called **staticEnemy** and change the image too this time to snake.

Check your code with the example below.
![Static Enemy Block](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-add-an-enemy/master/images/addStaticEnemy2.png)

### Create a Collision Listener

We now code what happens when our player overlaps with the enemy our **staticEnemy**.
Drag in an on player overlap with block from Sprites. Set the second value to be **Enemy**.
Inside the block drag in from Game block of **game over** and keep it set to **Lose**.

![Static Enemy Block](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-add-an-enemy/master/images/addStaticEnemy3.png)


## Test your game and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects.
In this case check that each time you add in a red block in your level tilemaps an enemy appears
and that when you touch the enemy the game ends with a Game Over message.

To check that you are making the most of this pattern you can ask yourself the following questions:

* Do you have any enemies in places that make it tricky for your player when they jump. 

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts. 
Find more on the [Game Pattern page](gamePatterns.md). 

As a next step you may find you want to increase the challenge even more perhaps by adding moving enemies. Or you may find
that you want to balance out the increase of challenge that these hazards have brought and add player lives.
