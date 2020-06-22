# Remixing a Platformer Game - Change Level Shape

In this tutorial we will learn how to **change the shape of our Levels** in our platformer.
If you want to understand more about how the starting code of the template works then you can follow [this tutorial](https://arcade.makecode.com/beta#tutorial:https://github.com/mickfuzz/mca_platformer_tutorial/tutorialPartOne)
 to create the game step by step.

## About this Game Pattern

![mechanics space polish and systems](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/gameMechanics_more_levels.jpg)

* **Name:** Change Level Shape

* **Description:** You may want to make your level longer or you may want to change the shape of one or more levels completely so they
have to jump up instead of travelling from left to right.

* **Need for Pattern:** Having **different shaped levels** is a way of making the game seem more exciting to explore.
It may also change the nature of your game especially if you make  your player climb up or fall down a level which is
tall and thin.  

* **Related Game Patterns:** Add More Levels [related]

* **Coding Concepts involved:** [Data](learningDimensions#data), [Events](learningDimensions#events)

* **Links to other Computing Patterns:** , [Change Listener](learningDimensions#change-listener)

## How to implement this Pattern in MakeCode

### Change the width of your level to make it longer

The most simple way to add this game pattern is to make your level length longer.
To do this click on your tilemap image and click on the numbers at the bottom left to change them.

The first one is the width so try changing that from 20 to 40. This make the level twice as long. Fill in the
blank space to add your level design.

### Change the shape of your level.

Another way to radically change the feel of your game is to make it tall and thin. Try this out by making the
second value (the height) much higher than first value (the width)

![change level shape](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/changeLevelShape.png)

If you want your player to start at the bottom then you'll need to change your starting position. You may need to do some maths.
The position is in pixels. If each square on the tilemap is 16 pixels and it is 40 squares high then the screen will be 40 x 16 pixels
high. You can set your player position based on that.

## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects. For example,  
you can ask yourself the following questions:

* Check your levels aren't too long and therefore feel boring

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts.
Find more on the [Game Pattern page](gamePatterns.md).
