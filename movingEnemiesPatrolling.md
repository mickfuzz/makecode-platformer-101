# Moving Enemies - Patrolling

![ moving enemies image](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/patterns/gameMechanics_patrollingenemies.jpg)

* **Name:** Patrolling Enemies

* **Description:** In this pattern the enemy moves around in a particular area in a repeating pattern. This movement is called patrolling. The enemy does not try to seek out the player.

* **Need for Pattern:** Having a **pattern name** is a way to increase the challenge of the player to reach goals and to collect food.
It also gives a sense of movement and excitement to the game.

* **Related Game Patterns:** Add Static Enemy [required], Jumping on Enemies [related]

* **Coding Concepts involved:** [Data](learningDimensions#data),  [Events](learningDimensions#events)

* **Links to other Computing Patterns:** , [Change Listener](learningDimensions#change-listener), [Systems Dynamics](learningDimensions#systems-dynamics)  

## How to implement this Pattern in MakeCode

### Step by Step instructions

A common pattern or mechanic in a game is to make the enemy move back and forward like a soldier on patrol. The easiest
way to do this is to create wall blocks which the enemy bounces between. We can call these kinds of enemies bumpers.

This tutorial assumes you have already added a static enemy pattern. We are going to add another kind of enemy in the same way.
To do this duplicate the  **for element** loop inside your **create level** function and add it back into the function.

We need to edit our tilemap and add a new colour of tile to our tilemap and place one in a location where it can bump between walls. In this example we will use a blue block.

![add another tile](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/addMovingEnemy1.png)

In our createLevels function, we are going to create a loop which finds all the blue blocks and does something with them. Follow the code example below to do this. You may recognise this pattern from the way that we create food in our game.  

![Change loop elements1](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/addMovingEnemy2.png)

We need a new kind of sprite called a Bumper. To do this we’ll have to make a new kind of sprite. In the **Set My Sprite** to block click on the type of sprite and select **Add a new kind**. 

![ patrolling enemies 1](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/patrol1.png)


When this is done you can select it from the lists.
We will also set our enemy heading off in a left or right direction. Set the velocity of our moving enemy to 50 (moving right) or -50 (moving left)



We need to set a Collision Listener so that the game is over if the player touches our moving enemy so create a Listener block
as below.

![Game over elements](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/addMovingEnemy3.png)

Then we need to make our bumper enemy change direction when it hits a wall block. You can do this by copying the following block.
You can see the green block is a familiar pattern where we loop through all the sprites of a particular type in this case.   

![ patrolling enemies 2](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/patrol2.png)


## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects.

To check that you are making the most of this pattern you can ask yourself the following questions:

* Are your blocks placed in the right place to make sure you enemies patrol in the right places
* Can place patrolling enemies towards the end of your game in a way that makes it tricky to get past them?

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts.
Find more on the [Game Pattern page](gamePatterns.md).

This pattern may make your game much more challenging. To balance it out a potential next step may be to
add the Jump on Enemies pattern to your game if you haven't already.
