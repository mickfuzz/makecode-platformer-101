# Remixing a Platformer Game - Simple Graphical Effects

In this tutorial we will add a **simple Graphical Effects** to our platformer.
If you want to understand more about how the starting code of the template works then you can follow [this tutorial](https://arcade.makecode.com/beta#tutorial:https://github.com/mickfuzz/mca_platformer_tutorial/tutorialPartOne)
 to create the game step by step.

## About this Game Pattern

![mechanics space polish and systems](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/gameMechanics_more_levels.jpg)

* **Name:** Simple Graphical Effects

* **Description:** A common pattern is to add graphical effects when things happen in the game. For example the look of a player may change
when they get zapped as a way of showing their death, or you can animate food when it is collected, or enemies when they get zapped. 

* **Need for Pattern:** Having a **graphical effects** is a way of increasing the excitement of the game and giving game players 
feedback on what happens in the game. 

* **Related Game Patterns:** Jumping on Enemies [related] 

* **Coding Concepts involved:** [Events](learningDimensions#events)

* **Links to other Computing Patterns:** , [Change Listener](learningDimensions#change-listener)

## How to implement this Pattern in MakeCode

### Animate Food Collection

Click on the plus sign next to the **destroy otherSprite** block and you can choose from many effects that happen to your 
sprite when the Food gets collected and how soon that effect happens. In the block below the confetti effects happens very quickly
after the Food is touched. 

![Animate Food Collection](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/graphicalEffects1.png)

### Animate Enemy getting Zapped

This requires you to have added the Jumping on Enemies pattern. In the **on sprite of kind Player overlaps otherSprite of kind Enemy**
condition listener loop click on the plus sign to the **destroy otherSprite** block and you can choose from many effects that happen to your 
sprite when the Food gets collected and how soon that effect happens. 

![Animate Enemy getting Zapped](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/graphicalEffects2.png)


## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects. 

To check that you are making the most of this pattern you can ask yourself the following questions:

* Have you animated all of the events that happen in your game? 
* Are the timings right for your game or are they too long or short?

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts. 
Find more on the [Game Pattern page](gamePatterns.md). 

A next step you might want to try is to add sound effects when things happen. 
          
