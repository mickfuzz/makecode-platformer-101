# Remixing a Platformer Game - Jumping on Enemies to Zap them

In this tutorial we will add the  **jumping on enemies to zap them** pattern to our platformer.
If you want to understand more about how the starting code of the template works then you can follow [this tutorial](https://arcade.makecode.com/beta#tutorial:https://github.com/mickfuzz/mca_platformer_tutorial/tutorialPartOne)
 to create the game step by step.

## About this Game Pattern

This game pattern is one of many you can add to your Platformer in this course.

![Jumping on Enemies to Zap them](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/gameMechanics_jumping.jpg)

* **Name:** Jumping on Enemies to Zap them

* **Description:** In many games players shoot enemies. In some platformers they get rid of them by jumping on them instead. 
If the player is descending from a jump when they touch the enemy the player is zapped and in this case dissapears. 

* **Need for Pattern:** Being able to jump on an enemy is a good way of clearing the area you want to explore. You may need to have a 
clear space to be able to jump up to a high platform for example. Some platformers do have a 
shooting mechanic as well but using this pattern and sticking with jumping also keeps the game simple (in a good way).

* **Coding Concepts involved:** [Data](codingConcepts#data), [Change Listener](widerPatterns#change-listener)

* **Links to other Computing Patterns:** [Systems Dynamics](widerPatterns#systems-dynamics),

* **Related Game Patterns:** You'll need to have added the **Add Enemies** pattern to your game before you can add this one. 

## How to implement this Pattern in MakeCode

### Add a Condition for the Overlap Listener block

We want the enemy to zap the player if they overlap normally or if the player is jumping up. But we want the player to 
zap the enemy if they are travelling on the down part of their jump. 

To do this we will check the Player's x axis velocity. As the numbers are measured from the top of the screen going down, if it is greater than 0 then the player is travelling in the down direction. 

Check if that’s true using the code blocks below, and if that isn’t the case then set the game to game over. 

![Jumping on Enemies to Zap them](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/jumpOnEnemies1.png)

The blocks in the **else** section may be different for example if you are using player lives, you will want your player to lose a life instead. 

## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects.

To check that you are making the most of this pattern you can ask yourself the following questions::

* When you add this mechanic you may be making the game much easier. Is there anything else you can do to make it more challenging? 
* Can you imagine the player experience? Is there anything you are fogetting or taking for granted?

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts. Find more on the [Game Pattern page](gamePatterns.md). 


