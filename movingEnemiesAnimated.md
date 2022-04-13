# Moving Enemies - Animated

![ moving enemies image](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/gameMechanics_animatedenemies.jpg)

* **Name:** Moving Enemies Animated

* **Description:** In this pattern a static enemy is animated to make some limited movements around its home position, for example bobbing or bouncing.

* **Need for Pattern:** Having a moving enemy is a way to increase the challenge of the player. It also gives a sense of movement and excitement to the game.

* **Related Game Patterns:** [Add Static Enemy](addStaticEnemy) [required], [Add Moving Enemies Patrolling](movingEnemiesPatrolling) [related]

* **Coding Concepts involved:** [Data](learningDimensions#data), [Events](learningDimensions#events), [Loops](learningDimensions#events)

* **Links to other Computing Patterns:** , [Change Listener](learningDimensions#change-listener), [Systems Dynamics](learningDimensions#systems-dynamics)  

## How to implement this Pattern in MakeCode


### We add enemies like we add food.
We add enemies like we add food to the game. Following this tutorial will add static enemies to your game.
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
Change the yellow square to a red one. Change the name of **food1** for the two blocks for it to mentioned.
I'll choose to create a new variable called **staticEnemy** and change the image too this time to snake.

Check your code with the example below.
![Static Enemy Block](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/addStaticEnemy2.png)

### Create a Collision Listener

We now code what happens when our player overlaps with the enemy our **staticEnemy**.
Drag in an on player overlap with block from Sprites. Set the second value to be **Enemy**.
Inside the block drag in from Game block of **game over** and keep it set to **Lose**.

![Static Enemy Block](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/addStaticEnemy3.png)

### Animate our Enemy (Optional)
We can add a bit more challenge to our game by making otherwise static enemies move around a fixed point using animation.

We alter our static enemies to animate them. To allow us to do this  go to  **Advanced > + Extensions > Add Animation**

![animated enemies image](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/addAnimatedEnemy1.png)
![animated enemies image](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/addAnimatedEnemy2.png)

We can now drag in an animate block which has an animation effect on it. Alter it so it matches the one below in our
**for each element** loop so that it applies to all Enemies. I change the type of animate from the drop down menu to use the
simple bobbing in place animation.

![animated enemies image](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/addAnimatedEnemy3.png)

You can see here that for simplicity's sake I've have not changed the variable name of staticEnemy. But you can change it or create a
new variable if you want to.

## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects.

To check that you are making the most of this pattern you can ask yourself the following questions:

* Are there other types of animations that suit your game.
* Where can you place the animated enemies to maximise the challenge to your game.

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts.
Find more on the [Game Pattern page](gamePatterns.md).

In this pattern we replace our static enemies with animated enemies. If you want to have both kinds of enemies then you can do this
by following the patterns shown in the **[add a patrolling enemy](movingEnemiesPatrolling)** tutorial.

Also this pattern may make your game much more challenging. To balance it out a potential next step may be to
add the **[jump on enemies](jumpOnEnemies)** pattern to your game if you haven't already.
