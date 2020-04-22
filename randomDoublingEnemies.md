# Remixing a Platformer Game - Random Doubling Enemies

In this tutorial we will add a **randomly spawning enemies that double in number**  to our platformer.
If you want to understand more about how the starting code of the template works then you can follow [this tutorial](https://arcade.makecode.com/beta#tutorial:https://github.com/mickfuzz/makecode-platformer-101)
 to create the game step by step.

## About this Game Pattern

![mechanics space polish and systems](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/gameMechanics_more_levels.jpg)

* **Name:** Randomly spawning enemies that double in number

* **Description:** This pattern adds enemies to our game that appear in random places. The number of enemies on the screen
also increases as the game progresses.

* **Need for Pattern:** Having a **randomly spawning enemies that double in number** is a way of increasing the Challenge in
our game. It is also an example of a feedback loop.

* **Related Game Patterns:** Add Static Enemy [related],

* **Coding Concepts involved:** [Data](learningDimensions#data), [Loops](learningDimensions#loops), [Events](learningDimensions#events)

* **Links to other Computing Patterns:** [Systems Dynamics](learningDimensions#systems-dynamics), [Reinforcing Feedback Loops](#reinforcing-feedback-loops)

## How to implement this Pattern in MakeCode

### Create our Random Enemy

We will create our randomly appearing enemy by creating an game update event that updates every 5 seconds to start with.
This will create an enemy of a type projectile that starts at the side of the screen and moves left.
So the enemy doesn't always start in the same place we will make the height value (y) random. See the screen shot below.

![random doubling enemies ](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/randomDoublingEnemies.png)

We now code a listener event that creates game over if there is an overlap.

![random doubling enemies ](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/randomDoublingEnemies2.png)

### Increase Spawn Time

A common pattern is to increase the spawn time of our enemies to increase the challenge.
To do this we will create a new variable at the start of our game called spawnTime.
Replace our value in the previous game update event with this variable.

![random doubling enemies ](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/randomDoublingEnemies2.png)

We now need to start to decrease this spawnTime variable. One easy way of doing that is to half the value every time the
event runs.
TO COME
## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects. For example, is x right?

To check that you are making the most of this pattern you can ask yourself the following questions:

* Now you have a double jump should you reduce the normal jump height (via changing the jump velocity or gravity effecting the player)
* Are there any parts of your game that you can only access via a double jump

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts.
Find more on the [Game Pattern page](gamePatterns.md).

Some next steps you might want to add may be x or y.
