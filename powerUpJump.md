# Remixing a Platformer Game - Power Up Higher Jump

In this tutorial we will add a **Power Up Higher Jump** ability to our platformer.
If you want to understand more about how the starting code of the template works then you can follow [this tutorial](https://arcade.makecode.com/beta#tutorial:https://github.com/mickfuzz/mca_platformer_tutorial/tutorialPartOne)
 to create the game step by step.

## About this Game Pattern

![power up higher jump](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/gameMechanics_more_levels.jpg)

* **Name:** Power Up Higher Jump

* **Description:** The player is able to jump higer if they collect a token that acts as a way of powering up their
abilities.

* **Need for Pattern:** Having a **Power Up Higher Jump** is a way of increasing the interest and challenge of our game.
The designer is able to create areas of the game that the player can only get to if they collect the power up.

* **Related Game Patterns:** Add Static Enemy [related]

* **Coding Concepts involved:** [Data](learningDimensions#data), [Loops](learningDimensions#loops), [Events](learningDimensions#events)

* **Links to other Computing Patterns:** , [Change Listener](learningDimensions#change-listener), [Input Event](learningDimensions#input-event), [Systems Dynamics](learningDimensions#systems-dynamics)

## How to implement this Pattern in MakeCode

### Create our power up sprite

To create a power up we will replicate the for element loop used to display the
Food elements on our game. So the first step is to duplicate that and to make changes to the values.
You can find more detailed instructions on how to do this is the create static enemeies pattern.
To start change your level Tilemap design to add a new colour tile to act as our power up and change
the design to include an area that the player would not be able to access with their normal jump.

![power up higher jump](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/powerUpHigherJump.jpg)

Follow the code pattern shown in the screenshot below to make the power up appear in our game.
![power up higher jump](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/powerUpHigherJump2.jpg)

### Create a new Variable

To be able to change the jump height of our player we will need to create a new variable for our game.
This will then be used when the player presses the jump button. To do this create a new variable called
jumpVelocity and and set it to the value you have in your on **A button pressed** input listener.

![power up higher jump](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/powerUpHigherJump3.jpg)
### Change Input Listener
You can now replace the original velocity y (vy) value with this new variable.

![power up higher jump](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/powerUpHigherJump4.jpg)

### Create the new Variable Value
Then we will add a condition listener to see when the player is overlapping this power up. When they do
we can make the power up dissappear and increase the velocity of the players jump. By increasing
the value of the variable that we have just created.

![power up higher jump](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/powerUpHigherJump4.jpg)


## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects.

To check that you are making the most of this pattern you can ask yourself the following questions:

* Can you jump up to your target area only after you collect your power up?
* Maybe you can make it tricky to access some areas when you have a higher jump, this increases the challenge by making
the player be careful about the order they do things.

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts.
Find more on the [Game Pattern page](gamePatterns.md).
