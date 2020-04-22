# Remixing a Platformer Game - Power Up Speed

In this tutorial we will add a **Power Up Speed** ability to our platformer.
If you want to understand more about how the starting code of the template works then you can follow [this tutorial](https://arcade.makecode.com/beta#tutorial:https://github.com/mickfuzz/makecode-platformer-101)
 to create the game step by step.

## About this Game Pattern

![power up higher speed](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/gameMechanics_more_levels.jpg)

* **Name:** Power Up Player Speed

* **Description:** The player is able to move faster if they collect a token that acts as a way of powering up their
abilities.

* **Need for Pattern:** Having a **Power Up Faster Player Speed** is a way of increasing the interest and challenge of our game.
The designer is able to create time or enemy related challenges that the player can only beat if they collect the power up.

* **Related Game Patterns:**  Add Timer [required], Following Enemies [related], [Change Shape of Levels](changeLevelShape)[related]

* **Coding Concepts involved:** [Data](learningDimensions#data), [Loops](learningDimensions#loops), [Events](learningDimensions#events)

* **Links to other Computing Patterns:** , [Change Listener](learningDimensions#change-listener), [Input Event](learningDimensions#input-event), [Systems Dynamics](learningDimensions#systems-dynamics)

## How to implement this Pattern in MakeCode

### Requirements
This tutorial assumes you have a timer on your platformer.

### Create our power up sprite
To create a power up we will replicate the for element loop used to display the
Food elements on our game. So the first step is to duplicate that and to make changes to the values.
You can find more detailed instructions on how to do this is the create static enemeies pattern.
To start change your level Tilemap design to add a new colour tile to act as our power up and change
the value of your timer to be one the player would not be able beat if they travelled at normal speed.

![power up speed](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/powerUpSpeed1.jpg)

In the example above you can see that the layout of the level is longer than the starting one. This
is due to this pattern working well will longer levels.

Follow the code pattern shown in the screenshot below to make the power up appear in our game.
![power up speed](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/powerUpSpeed2.jpg)

### Create a new Variable

To be able to change the speed of our player we will need to create a new variable for our game.
This will then be used when the player presses left and right buttons. To do this create a new variable called
playerSpeedVelocity and and set it to the vx value you have in your **move sprite with buttons** block.

You can now replace the original velocity x (vx) value with this new variable.
![power up speed](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/powerUpSpeed3.jpg)


### Create the new Variable Value
Then we will add a condition listener to see when the player is overlapping this power up. When they do
we can make the power up dissappear and increase the velocity of the players speed. By increasing
the value of the variable that we have just created.
![power up speed](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/powerUpSpeed4.jpg)

## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects.
To check that you are making the most of this pattern you can ask yourself the following questions:

* Can you complete the level only if you after you collect your power up?

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts.
Find more on the [Game Pattern page](gamePatterns.md).

As a follow up to this maybe you can make changes to the timer for different levels.
