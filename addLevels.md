# Add More Levels

![mechanics space polish and systems](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/patterns/gameMechanics_more_levels.jpg)

* **Name:** Add More Levels

* **Description:** The player reaches the goal of the first Level of the platformer and then progresses to the next level (and beyond)

* **Need for Pattern:** Having more than one level is a way increasing the length and challenge of the game. You can also bring other elements
of design and even game mechanics to new levels.

* **Coding Concepts involved:** [Data](learningDimensions#data), [Variables](learningDimensions#variables),

* **Links to other Computing Patterns:** [Systems Dynamics](learningDimensionss#systems-dynamics), [Change Listener](learningDimensions#change-listener)

## Putting the Pattern into Practice
### Create a "level" variable
Now we will reate a  variable to hold the number of level we are on. We will then be able to change it.
We create this level variable at the end of our ***on start*** loop.

![Create Variable](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/addLevels2.png)

![Add set Variable](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/addLevels3.png)

### Create a new chooseLevel Function
Create a new Function by clicking on the **Advanced** tab on our toolbar, then  **Functions**
And then click **Make a Function**. Enter chooseLevel in the white box.

![Add set Variable](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/addLevels4.png)

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

### Change the  overlap (change) Listener between Player and Goal Sprite  
In our game we have a listener which is always checking to see if there is an overlap between our Player and the Goal Sprite.  
In our starting template this lists only a Game Over - Lose block. Delete that block so the on overlap listener block is empty.

![Remove Game over Block](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/addLevels1.png)

We will replace it with code that changes the level number and builds a new level and moves the player back to the starting point.

### Code what happens when we complete a level
In the **on sprite of kind Player overlaps Door** listener block add a **change level by 1** block.
Next add call createLevels block to recall the function that does the work of adding the different blocks to the game.

![insert change levels block](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/addLevels7.png)

### Remove any thing that might remain from the last level

If you are not careful then some of the things from the last level like food or enemies may carry over to your next level. 

From the **Sprites** area drag in a **destroy all sprites of kind xx** block to the start of the **createLevel** function. Change the option to **Food** or **Enemy** or what ever other kinds of object you may need to clear for the previous level.

![Add set Variable](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/addLevels8.png)

In the image above all previous items of food are removed. You may need to several of these kinds of blocks for different types of items you add to your game.  

## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects.
For example check that each time you touch the end goal you progress by a level and the design matches.

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts.
Find more on the [Game Pattern page](gamePatterns.md).
