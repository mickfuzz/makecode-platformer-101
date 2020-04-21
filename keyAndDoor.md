# Remixing a Platformer Game - Key and Door

In this tutorial we will add a key to open a end door to our platformer levels.
If you want to understand more about how the starting code of the template works then you can follow [this tutorial](https://arcade.makecode.com/beta#tutorial:https://github.com/mickfuzz/makecode-platformer-101)
 to create the game step by step.

## About this Game Pattern

![keys and doors](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/patterns/gameSpace_keysDoors.jpg)

* **Name:** Key and Door

* **Description:** The player needs to collect a key before they can exit the level of the platformer game.

* **Need for Pattern:** Having a **Key and Door** is a common pattern which adds to a sense of exploration to the game. You can use this in
combination with using points to collect other objects.

* **Related Game Patterns:** Add Levels [suggested before adding this one], Collect Points [related]

* **Coding Concepts involved:** [Data](learningDimensions#data), [Loops](learningDimensions#loops), [Events](learningDimensions#events)

* **Links to other Computing Patterns:** , [Change Listener](learningDimensions#change-listener), [Input Event](learningDimensions#input-event), [Systems Dynamics](learningDimensions#systems-dynamics)  

## How to implement this Pattern in MakeCode

### Step by Step instructions
In this simple application of the key and door pattern we will keep our current end goal, which in our starting template was the chest,
and add in a new kind of sprite called a key which the player needs to collect before touching the end goal has an effect.

First add in a new tile colour to represent our key in your Tilemap plan of the first level.
There are more detailed steps on how to do this in the add Static Enemy instructions.
But in short create one tile to represent your location of your key.

To do this click on your tilemap to bring up the editor.
Click on  **My Tiles > + (plus sign)** and fill this new tile entirely with one colour.
Then select that tile and place one tile in your level design where you want your key to be.
This is shown in the screenshot below.

![key and door 1 ](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/keyDoor1.png)

Follow the same kind of patter used in adding food to the level by adding a for element loop to look for the
new coloured squares. This is explained in more detail in adding a static enemy pattern.
Change the names of the variable and add in a new sprite type called Key.
Change the image by drawing a key too. This is shown in the screenshot below.
You can change the image of your end goal to a door also if you want to.

![key and door  ](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/keyDoor2.png)

Add in a condtion listener that collect the key when the player touches it. We need to
know if the player has the key so we will create a new variable called **hasKey**
We will set this to 1 to show that the player has one key.

![key and door  ](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/keyDoor3.png)

Then only progress if the player is touching the end goal and the  **hasKey** variable
has been change to one, as in the screenshot below.

![key and door 4 ](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/keyDoor4.png)

## Test your Changes and Next Steps

Test your game to check that your changes have the desired behaviour and that there are no side effects. For example, is x right?

To check that you are making the most of this pattern you can ask yourself the following questions:

* Now you have a double jump should you reduce the normal jump height (via changing the jump velocity or gravity effecting the player)
* Are there any parts of your game that you can only access via a double jump

This Game Pattern is one of many allowing you to make improvements to your platform game and to learn coding and wider computing concepts.
Find more on the [Game Pattern page](gamePatterns.md).

Some next steps you might want to add may be x or y.
