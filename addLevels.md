# Remixing a Platformer Game - Add More Levels

## Add More Levels
### Introduction

In this tutorial we will **add more levels** to our platformer.
If you want to understand more about how the starting code of the template works then you can follow [this tutorial](https://arcade.makecode.com/beta#tutorial:https://github.com/mickfuzz/makecode-platformer-101)
 to create the game step by step.

#### About this Game Pattern

This game pattern is one of many you can add to your Platformer in this course.

![mechanics space polish and systems](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/patterns/gameMechanics_more_levels.jpg)

* **Name:** Add More Levels

* **Description:** The player reaches the goal of the first Level of the platformer and then progresses to the next level (and beyond)

* **Need for Pattern:** Having more than one level is a way increasing the length and challenge of the game. You can also bring other elements
of design and even game mechanics to new levels.

* **Coding Concepts involved:** [Data](codingConcepts#data), [Change Listener](widerPatterns#change-listener)

* **Links to other Computing Patterns:** [Systems Dynamics](widerPatterns#systems-dynamics),


### Change the  overlap (change) Listener between Player and Goal Sprite  
In our game we have a listener which is always checking to see if there is an overlap between our Player and the Goal Sprite.  
In our starting template this lists only a Game Over - Lose block. Delete that block so the on overlap listener block is empty.

![Remove Game over Block](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/patterns/addLevels1.png)

We will replace it with code that changes the level number and builds a new level and moves the player back to the starting point.


### Create a "level" variable
Now we will reate a  variable to hold the number of level we are on. We will then be able to change it.
We create this level variable at the end of our ***on start*** loop.

![Create Variable](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/patterns/addLevels2.png)

![Add set Variable](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/patterns/addLevels3.png)


### Create a new chooseLevel Function
Create a new Function by clicking on the **Advanced** tab on our toolbar, then  **Functions**
And then click **Make a Function**. Enter chooseLevel in the white box.

![Add set Variable](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/patterns/addLevels4.png)

![Add set Variable](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/patterns/addLevels5.png)


### Move tilemap to new Function
Drag only the  **set tilemap to** into the new **chooseLevel** function by holding down **Control** on your Keyboard while you drag the block.
Right click and select **Format Code** to make the screen tidy.


### Add a link to the new function
Drag in the **call chooseLevel** from **Functions** to the end of the begining of the **createLevel** function.

![game level four](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/new_level_4.png)

### Create the Logic switcher for the Level Design
Now add a Logic block **if true then** inside the **chooseLevel** block
Move the the **set tilemap to**  inside the logic block.
In the new **if true then** block replace **true** with at **0 = 0** block from Logic section.

Right click on the Logic block **if level = 0** and duplicate it.
Change 0 to 1 in the second block and drag it back into the **chooseLevel** function.

Repeat the process again  changing the **level** number  to two.
Move a **game over - win** block into to this gap and delete the **tilemap** block.  

![game level four](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/addLevels5.png)


### Code what happens when we complete a level
In the **on sprite of kind Player overlaps Door** listener block add a **change level by 1** block.
Next add a **set mySprite position to x 10 y 100**
Then add a **createLevels** block from **Functions**

![game level four](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/new_level_7.png)



## Test your game, Invite Playtesing and Reflecting

**This tutorial is now complete.**

You can test your game to check that it has the desired behaviour.

AND???

This tutorial is one of many allowing you add different Game Element on the home page of this Platformer Making Course.
