# Add Player Lives

![mechanics space polish and systems](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/gamemechanic_extralives_800.png)

* **Name:** Add Player Lives

* **Description:** The player starts the game with a number of the lives When the Player is zapped, or runs out of health the play restarts but with one less life.  

* **Need for Pattern:** Having player lives is a way of reducing the frustration of a challenging game. For example players normally restart from the level they got lost their life on rather than going back to the very beginning.

* **Related Game Patterns:** Before adding this pattern you'll need something that can zap you. So add a pattern like
**[add Static Enemy](addStaticEnemy)** or a moving enemy.  

* **Coding Concepts involved:** [Variables](learningDimensions#variables)

* **Links to other Computing Patterns:** [Systems Dynamics](learningDimensions#systems-dynamics),[Change Listener](learningDimensions#change-listener)


### Adding a starting amount of lives
We can add in the starting number of lives.
To do this drag in from **Info** a  **set lives to 3** block to the
beginning of the on start loop.

![mechanics space polish and systems](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/addLives.png)

### Change the overlap loop for our Enemy
In this game previously you may have had code where the player overlapping with a Static Enemy would be Game Over with the player losing.

![lose a point](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/addLives3.png)

Another possibility is that you may have moving enemies with a different code structure. You can change to replace the Game Over lose block with a **change lives by -1** block.

![lose a point](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/addLives2.png)


## Reflecting on what's happening

**[Variables](learningDimensions#variables):** In this example you are using a [Variable](learningDimensions#variables) of called life to keep track of the player lives. In this example you start with three and you update the value of that [Variable](learningDimensions#variables) everytime you bump into an enemy.

**[Change Listener](learningDimensions#change-listener):** The **on sprite kind overlap** block is always listening out for a change where if there is a new overlap with an enemy the programme will run the code inside that block. This kind of [Change Listener](learningDimensions#change-listener) is often used in computer programmes to react to new situations.

**[Systems Dynamics](learningDimensions#systems-dynamics):** The use of new lives means that the balance of the game will be altered. This may make it easier so you may need to balance this out by making something in your game harder. This process of balancing out systems elements allow us to explore [Systems Dynamics](learningDimensions#systems-dynamics).

## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects.
For example check that each time you touch an enemy your number of lives goes down by one.

There is a known side effect with some kinds of enemies where you lose more than one life. To avoid this you may need to
**[make Player Immune](makePlayerImmune)** pattern

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts.
Find more on the [Game Pattern page](gamePatterns.md).
