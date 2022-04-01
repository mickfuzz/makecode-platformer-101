# Pattern Name

![mechanics space polish and systems](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/game_polish_makeplayerimmune.jpg)

* **Name:** Make Player Immune from Enemies

* **Description:** The player is not able to be zapped by enemies.

* **Need for Pattern:** Having **player immunity** is often needed if you have a system of lives. If you lose a life
but don't move your player back to the start in a safe place, then the continuing overlap will cause you to lose all your
lives at once.

* **Related Game Patterns:** Add Patrolling Enemy [required], Add Player Lives [required],

* **Coding Concepts involved:** [Events](learningDimensions#events)

* **Links to other Computing Patterns:** , [Change Listener](learningDimensions#change-listener),

## How to implement this Pattern in MakeCode

### Step by Step instructions

This pattern is needed when you have player lives and enemies. There is often a side effect where a player can be overlapped
with an enemy. The player needs to be made immune from enemies so that they cannot be harmed and they may also need to be moved.
This tutorial assumes you have patrolling enemies and player lives patterns added to your game.

### Add a delay and make Immunity obvious

In your **overlap listener** for the Bumper enemy type we will also play a sound to make it obvious that the player has been zapped.  
We will also hange the look of the player sprite.

In the loop you will add in a **pause** when you lose a life. The **pause** means you cannot be zapped by players in this period.  

![make player immune](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/makePLayerImmune.png)


## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects. For examples if you have more than
one type of enemy, like simple static enemies, you will need to add this code in those overlap listeners too.

To check that you are making the most of this pattern you can ask yourself the following questions:

* Is the length of delay right or does it need to be longer or shorter?

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts.
Find more on the [Game Pattern page](gamePatterns.md).
