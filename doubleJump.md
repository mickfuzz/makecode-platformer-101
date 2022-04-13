# Double Jump

![mechanics space polish and systems](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/patterns/gameMechanics_doublejump.jpg)

* **Name:** Double Jump

* **Description:** The player is able to jump in the middle of another jump but only once. Pressing the jump button a third time with have
no effect.

* **Need for Pattern:** Having a double jump is a way of allowing the player to access areas not possible with a single jump. Double Jumps
also require good timing from the player too so this can increase challenge depending on the design of your game.

* **Related Game Patterns:** Jumping on Enemies [related]

* **Coding Concepts involved:** [Data](codingConcepts#data), [Change Listener](widerPatterns#change-listener)

* **Links to other Computing Patterns:** [Systems Dynamics](widerPatterns#systems-dynamics),

## How to implement this Pattern in MakeCode

### Create a "canDouble Jump" variable
We need to create a variable called canDoubleJump. Now add a block  at the start of our game and set it to true to start with.

![Double Jump 2](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/doubleJump_2.png)


### Create a Logic block to test if player can jump or not

Then you need to use blue logic blocks to check to only jump if  

* the bottom of your player (mySprite) is touching the floor (wall) or
* or if (else if) canDoubleJump is true

![Double Jump 3](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/doubleJump_3.png)

Once the player has used up their double jump ability, you set the canDoubleJump variable to false. This stops the player from being able to jump more than twice. 

### Reset canDoubleJump variable
Then we must create to code to reset the canDoubleJump variable when you touch the ground again. To do this create a on game update loop and put a logic block in there which will turn canDoubleJump true when you are touching the ground again.

![Double Jump 1](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/doubleJump_1.png)


## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and no side effects.
To check that you are making the most of this pattern you can ask yourself the following questions:

* Now you have a double jump should you reduce the normal jump height (via changing the jump velocity or gravity effecting the player)
* Are there any parts of your game that you can only access via a double jump

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts. Find more on the [Game Pattern page](gamePatterns.md).
