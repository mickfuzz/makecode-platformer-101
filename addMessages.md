# Add Written Messages

![mechanics space polish and systems](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/game_polish_storywithmessages.jpg)

* **Name:** Add Written Messages

* **Description:** The game maker can display messages to the player at the start of the game. You can also add messages when something happens in the game.  

* **Need for Pattern:** Having **written messages** is a way of giving playing instructions to the player at the start of the game, giving them clues as they progress or just making the game more fun to play by adding story elements.

* **Related Game Patterns:** Add Graphical Elements [related]

* **Coding Concepts involved:** [Data](learningDimensions#data), [Events](learningDimensions#events)

* **Links to other Computing Patterns:** , [Change Listener](learningDimensions#change-listener)

## How to implement this Pattern in MakeCode

### Step by Step instructions

Find the splash block under the Game section and drag one or more blocks to the beginning of the on start block.

![add messages](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/addMessages.png)

You can also get your player to say something when an event happens. For example lets get the player to say Yum when collecting an apple.

Alter the overlap event code block to add in a sprite say block and set the time.         

![add messages](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/addMessages2.png)

## Extra Challenge

You can give your Levels name that come up before your players play them. To do this you will need to have added different levels to your game.

To start with we will create an Array (which is a kind of list) of the different names of the levels.

![add a list](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/game_polish_messages_2.jpg)

Now add a splash message at the start of your createLevel function. Note how you can use the level value to pick the right message from your list. 

![add a splash message](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/game_polish_messages_2.jpg)



## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects. For example,  
you can ask yourself the following questions:

* Check your messages aren't too long and disappear of the side of the screen
* Check that the messages appear in the right place

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts.
Find more on the [Game Pattern page](gamePatterns.md).
