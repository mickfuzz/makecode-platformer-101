# Remixing a Platformer Game - Collect all Food before Progressing

In this tutorial we will change the game so that the player has to collect all items of Food before they can  win the game or .
progress to the next level.
If you want to understand more about how the starting code of the template works then you can follow [this tutorial](https://arcade.makecode.com/beta#tutorial:https://github.com/mickfuzz/makecode-platformer-101)
 to create the game step by step.

## About this Game Pattern

![mechanics space polish and systems](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/gameMechanics_more_levels.jpg)

* **Name:** Collect all Food before Progressing

* **Description:** The player must collect all items of food before progressing. 

* **Need for Pattern:** Having our player  **Collect all Food before Progressing** is a way of increasing the challenge of a game. It 
works well in combination with having a timer. 

* **Related Game Patterns:** Add a Time [related], Add more Levels [related] 

* **Coding Concepts involved:** [Data](learningDimensions#data), 

* **Links to other Computing Patterns:** , [Change Listener](learningDimensions#change-listener)
## How to implement this Pattern in MakeCode

### Add a Logic Step into our Overlap Listener

To add this patterns we need to add some logic the overlap listener which checks to see if the player is touching the end goal. 
Drag in an **if then** logic block and follow up with a **0 = 0** operator comparison block.
From **Advanced > Arrays** drag a **length of array list** block into the first side of the comparison block.
![collect all food ](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/collectAllFood.png)

### Check the number of Food Items

Check the number of food items by replacing the list variable with a real list. In this case the list
of food items. To do this drag in from **Advanced > Arrays** a block that says **set sprite list to array of kind Player**.
Drag this into a blank area near our overlap listener as we only need on part of it. 

![collect all food ](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/collectAllFood2.png)

So Drag the blue block saying **array of kind player** inside the **length of array** block, and change Player to Food. 
Check with the screenshot below. 

![collect all food ](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/collectAllFood3.png)

## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects. For example, do you have to collect
all food or can you progress without doing that? 

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts. 
Find more on the [Game Pattern page](gamePatterns.md). 
          
