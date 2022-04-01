# Add a timer

![mechanics space polish and systems](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/patterns/game-mechanics_timer.png)

* **Name:** Add a Timer

* **Description:** The player is required to complete the level or another goal before the timer runs out.

* **Need for Pattern:** Having a **timer** is a way of creating challenge for the player. If you have more than one
level you can reduce the time allowed for the next level to increase the challenge as the game progresses.

* **Related Game Patterns:** [Add Player Lives](addLives) [related], [Add More Levels](addLevels) [related],  

* **Coding Concepts involved:** [Data](codingConcepts#data)

* **Links to other Computing Patterns:** [Systems Dynamics](learningDimensions#systems-dynamics), [Making Functions](learningDimensions#systems-dynamics)


## How to implement this Pattern in MakeCode

### Simple Timer for each level

Drag in from the **Info** section a block that reads countdown into the createLevels function.

Because this is in the createLvels function rather than in the on start function, this timer will reset everytime you reach a new level.

![add timer](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/addTimer1.png)

### Have different timer values for each level

One classic way of adding challenge to a game is to ask your player to solve the next level of your game in less time. If you want to have different values for your timer for each level. We will create an array variable which will contain a list of the different times.

From **Advanced > Arrays** drag in a **set list to array of** block to the end of the on start block above the **call createLevels** block.

![](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/addTimer2.png){width=90%}

Then change the variable list to one called **levelTimes** by clicking on it and selecting New Variable. Then change the times for each level. I'm setting the first level time to be 20 and the next one to be 15.

![](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/addTimer3.png)


If you haven't already drag in from the **Info** section a block that reads countdown into the createLevels function for each level.
Next from **Advanced > Arrays** drag in a **list get value at** block and add it to the countdown block, and include your  
levelTimes value at level, as you can see in the screenshot below.

![](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/addTimer4.png)


## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects.
To check that you are making the most of this pattern you can ask yourself the following question/s:

* Make sure you haven't made your game too hard or too easy get others to test it

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts.
Find more on the [Game Pattern page](gamePatterns.md).

Some next steps you might want to add may be add more Levels. If you do that then you will need to look at the pattern to add
different timings for different levels.
