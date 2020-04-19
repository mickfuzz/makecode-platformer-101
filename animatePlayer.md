# Remixing a Platformer Game - Animate Player

In this tutorial we will add a **player animation** to our platformer.
If you want to understand more about how the starting code of the template works then you can follow [this tutorial](https://arcade.makecode.com/beta#tutorial:https://github.com/mickfuzz/makecode-platformer-101)
 to create the game step by step.

## About this Game Pattern

![mechanics space polish and systems](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/gameMechanics_more_levels.jpg)

* **Name:** Animate Player

* **Description:** The player is animated using different 'frames'.

* **Need for Pattern:** This movement helps create a sense of dynamic movement and
can help the game player's immersion in the game.

* **Related Game Patterns:** Add Static Enemy [needed before adding this one], Jumping on Enemies [related]

* **Coding Concepts involved:** [Data](learningDimensions#data)

* **Links to other Computing Patterns:** , [Change Listener](learningDimensions#change-listener)

## How to implement this Pattern in MakeCode

### Simple Animation of Player

We will create a simple animation using different frames of our player.
To allow us to do this  go to  **Advanced > + Extensions > Add Animation**
Drag in the animation block that you see below.

![simple animation](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/animatedPlayer.png)

### Animated Walking and Jumping using Animation States
See the following https://makecode.com/_ecqJXwWrpJXw

To create more authentic animations which change the direction of the player, show them walking and still when not
moving we will use an animation with states. To start we will have three simple states moving **Left**, moving **Right**
and not moving i.e. **Idle**
![animate player states1 ](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/animatePlayer1.png)


## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects.

To check that you are making the most of this pattern you can ask yourself the following questions:

* Is your animation smooth?

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts.
Find more on the [Game Pattern page](gamePatterns.md).
