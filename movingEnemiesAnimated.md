# Remixing a Platformer Game - Moving Enemies Pt2 - Animated

In this tutorial we will add a **moving animated enemy** to our platformer.
If you want to understand more about how the starting code of the template works then you can follow [this tutorial](https://arcade.makecode.com/beta#tutorial:https://github.com/mickfuzz/mca_platformer_tutorial/tutorialPartOne)
 to create the game step by step.

## About this Game Pattern

![ moving enemies image](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/gameMechanics_moving_enemies.jpg)

* **Name:** Moving Enemies Animated

* **Description:** In this pattern a static enemy is animated to make some limited movements around its home position, for example bobbing or bouncing.

* **Need for Pattern:** Having a **pattern name** is a way to increase the challenge of the player to reach goals and to collect food.
It also gives a sense of movement and excitement to the game.

* **Related Game Patterns:** [Add Static Enemy](addStaticEnemy) [required], [Add Moving Enemies Patrolling](movingEnemiesPatrolling) [related]

* **Coding Concepts involved:** [Data](learningDimensions#data), [Events](learningDimensions#events), [Loops](learningDimensions#events)

* **Links to other Computing Patterns:** , [Change Listener](learningDimensions#change-listener), [Systems Dynamics](learningDimensions#systems-dynamics)  

## How to implement this Pattern in MakeCode

### Step by Step instructions

We can add a bit more challenge to our game by making otherwise static enemies move around a fixed point using animation. 
This tutorial assumes you have already added a static enemy pattern. 

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
