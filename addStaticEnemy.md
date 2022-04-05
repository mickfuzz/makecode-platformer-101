# Add a Static Enemy

![mechanics add a static enemy](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/gameMechanics_staticenemies.jpg)

* **Name:** Add a Static Enemy

* **Description:** Also known as a Hazard, a Static Enemy will kill or damage the health of the player if they touch it. These are often placed in tricky spots which the player is likely to bump into when jumping or trying to collect rewards.  

* **Need for Pattern:** Having hazards increases the challenge of a level, you can place hazards in a way that requires the player to time their jumps well and really control their movement.

* **Related Game Patterns:** Add Moving Enemies [related], Jump on Enemies [related]

* **Coding Concepts involved:** [Loops](learningDimensions#loops), [Events](learningDimensions#events)

* **Links to other Computing Patterns:** , [Change Listener](learningDimensions#change-listener), [Input Event](learningDimensions#input-event)  

## How to implement this Pattern in MakeCode


### Add Static Enemies to your Tilemap

Click on your tilemap. Create a totally Red tile in **My Tiles**. Add one or two red blocks to your first level.   

![Static Enemy Block](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/addStaticEnemy_b1.png)

You can also draw an enemy / hazard of your choice in My Tiles section. Click on the plus sign to do that. 

### Create a Collision Listener

We now code what happens when our player overlaps with our **staticEnemy**.
Drag in an **on sprite of kind player overlap with __ at location** from Scene.
Inside the block drag in from Game block of **game over** and keep it set to **Lose**.

![Static Enemy Block](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/addStaticEnemy_b1.png)

## Test your game and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects.
In this case check that each time you add in a red block in your level tilemap/s it should behave as a static hazard. When you touch the enemy the game ends with a Game Over message.


To check that you are making the most of this pattern you can ask yourself the following questions:

* Do you have any enemies in places that make it tricky for your player when they jump.

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts.
Find more on the [Game Pattern page](gamePatterns.md).

As a next step you may find you want to increase the challenge even more perhaps by adding moving enemies. Or you may find
that you want to balance out the increase of challenge that these hazards have brought and add player lives.
