# Remixing a Platformer Game - Jumping on Enemies to Zap them

In this tutorial we will add the  **jumping on enemies to zap them** pattern to our platformer.
If you want to understand more about how the starting code of the template works then you can follow [this tutorial](https://arcade.makecode.com/beta#tutorial:https://github.com/mickfuzz/makecode-platformer-101)
 to create the game step by step.

## About this Game Pattern

This game pattern is one of many you can add to your Platformer in this course.

![Jumping on Enemies to Zap them](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/patterns/gameMechanics_jumping.jpg)

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

### Add a condition of the Overlap Listener block

We need to compare you the player's height on the screen to that of the thing it is jumping on. 
OR COMPARE VELOCITY
As the numbers are measured from the top of the screen going down, the location of bottom of your sprite should be less in number
than that of the enemy sprite if it is above it. Check if that’s true using the code blocks below,
and if that isn’t the case then set the game to game over. 

The blocks in the **else** section may be different for example if you are using player lives, you will want your player to lose a life instead. 

## Test your Changes

Test your game to check that your changes have the desired behaviour and no side effects.

Ask yourself the following questions:

* When you add this mechanic you may be making the game much easier. Is there anything else you can do to make it more challenging? 
* Can you imagine the player experience? Is there anything you are fogetting or taking for granted?

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts. Find more on the [Game Pattern page](gamePatterns.md). 


