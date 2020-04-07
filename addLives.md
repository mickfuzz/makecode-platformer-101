# Remixing a Platformer Game - Add Player Lives

## Adding Player Lives
### Introduction

In this tutorial we will **add player lives** to our platformer.
To do this tutorial you will also need to have done one on *Add an Enemy*.
If you want to understand more about how the starting code of the template works then you can follow [this tutorial](https://arcade.makecode.com/beta#tutorial:https://github.com/mickfuzz/makecode-platformer-101)
 to create the game step by step.

#### About this Game Pattern

This game pattern is one of many you can add to your Platformer in this course.

![mechanics space polish and systems](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/patterns/gamemechanic_extralives_800.png)

* **Name:** Add Player Lives

* **Description:** The player starts the game with a number of the lives When the Player is zapped, or runs out of health the play restarts but with one less life.  

* **Need for Pattern:** Having player lives is a way of reducing the frustration of a challenging game. For example players normally restart from the level they got lost their life on rather than going back to the very beginning.

* **Related Game Patterns:** Before adding this pattern you'll need something that can zap you so add a pattern like
 **add static enemy** or let your player
**jump on enemies**.

* **Coding Concepts involved:** [Data](learningDimensions#data)

* **Links to other Computing Patterns:** [Systems Dynamics](learningDimensions#systems-dynamics),[Change Listener](learningDimensions#change-listener)


### Adding a starting amount of lives
We can add in the starting number of lives.
To do this drag in from **Info** a  **set lives to 3** block to the
beginning of the on start loop.

### Change the overlap loop for our Enemy
In this game previously the player overlapping with an Enemy would be Game Over with the player losing.
Now let's change to replace the Game Over lose block with a **change lives by -1** block


## Test your game and Next Steps
### Test your game and Next Steps
**This tutorial is now complete.**

You can test your game to check that each time you touch an enemy your number of lives
goes down by one.

This tutorial is one of many allowing you add different Game Element on the home page of this Platformer Making Course.
