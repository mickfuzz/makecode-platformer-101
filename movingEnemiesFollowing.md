# Moving Enemies - Following

![ moving enemies image](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/gameMechanics_followingenemies.jpg)

* **Name:** Moving Enemies Animated

* **Description:** In this pattern a static enemy is animated to make some limited movements around its home position, for example bobbing or bouncing.

* **Need for Pattern:** Having a **following enemy** is a way to increase the challenge of the player to reach goals and to collect food.
It also gives a sense of movement and excitement to the game.

* **Related Game Patterns:** [Add Static Enemy](addStaticEnemy) [required], [Add Moving Enemies Patrolling](movingEnemiesPatrolling) [related]

* **Coding Concepts involved:** [Data](learningDimensions#data), [Events](learningDimensions#events), [Loops](learningDimensions#events)

* **Links to other Computing Patterns:** , [Change Listener](learningDimensions#change-listener), [Systems Dynamics](learningDimensions#systems-dynamics)  

## How to implement this Pattern in MakeCode

### Step by Step instructions

This game mechanic works well when you have enough time to run away from these enemies or somehow get rid of them by shooting or jumping on them.
This tutorial assumes you have already added a static enemy pattern.

As with static enemeies, we need to edit out tilemap and add a new colour of tlle to our tilemap and place one in a location. In this case
be sure to change your design to add some black blocks.

![add another tile](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/addFollowingEnemy2.png)

Now follow the same kind of pattern for creating a static enemy but change the final blocks. I’ve chosen a small meteroite from the Gallery here. Having a small follower
looks good.  

Add a **set to follow** block from our Sprite section a **set followingEnemy to follow mySprite with speed 40**. Set this been to follow mySprite which is your player sprite.

![add another tile](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/addFollowingEnemy1.png)

In the block above I’ve change the speed of the bee to be slower at 40 than the default 100 as in this example the player just has to run away from the meteroite.

## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects.

To check that you are making the most of this pattern you can ask yourself the following questions:

* Does this pattern make your game too hard? If so do you need to slow down the followers or reduce how many there are?
* Are there enough obstacles to dodge around to slow the followers down?

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts.
Find more on the [Game Pattern page](gamePatterns.md).

This pattern may make your game much more challenging. To balance it out a potential next step may be to
add the **[jump on enemies](jumpOnEnemies)** pattern to your game if you haven't already.
