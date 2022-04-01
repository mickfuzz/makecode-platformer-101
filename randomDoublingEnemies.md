# Remixing a Platformer Game - Random Doubling Enemies


![random doubling enemies](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/gameChallenge_doublingenemies.jpg)

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

We will create our randomly appearing enemy by creating a forever loop which creates an enemy of a type projectile that
starts at the side of the screen and moves left.
So the enemy doesn't always start in the same place we will make the height value (y) random. See the screen shot below.
Add in a pause to the forever loop so it this new projectile happens every 5 seconds to start with.

![random doubling enemies ](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/randomDoublingEnemies6.png)

We now code a listener event that creates game over if there is an overlap.

![random doubling enemies ](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/randomDoublingEnemies2.png)

### Increase Spawn Time

A common pattern is to increase the spawn time of our enemies to increase the challenge.
To do this we will first create a new variable at the start of our game called spawnTime.
Replace our value in the previous fover loop  with this variable.

![random doubling enemies ](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/randomDoublingEnemies7.png)

We now need to start to decrease this spawnTime variable. One easy way of doing that is to half the value every time the
event runs by dividing it by two. This creates a reinforcing feedback loop so things might get crowded with projectiles very soon.

![random doubling enemies ](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/randomDoublingEnemies5.png)

Your player will have to be fast.

## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects.

To check that you are making the most of this pattern you can ask yourself the following questions:

* Does the number of enemies increase at too fast a rate? If so how can you change the rate do it doesn't double?
* Would you want to have a maximum number of enemies on the screen at once or a maximum rate of increase to avoid?

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts.
Find more on the [Game Pattern page](gamePatterns.md).
