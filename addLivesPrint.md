### @activities true

# Remixing a Platformer Game - Add Player Lives

## Adding Player Lives 
### Getting Started @unplugged

In this tutorial we will **add player lives** to our platformer.

This tutorial depends on the code of one to add an enemy located here. 

If you want to understand more about how the starting code of the template works then you can follow [this tutorial](https://arcade.makecode.com/beta#tutorial:https://github.com/mickfuzz/makecode-platformer-101)
 to create the game step by step.

This tutorial is one of many allowing you add different Game Element on the home page of this Platformer Making Course.

### Adding a starting amount of lives @fullscreen
We can add in the starting number of lives.
To do this drag in from ``||info:info||`` a block  ``||info:set lives to 3 ||`` add this to the 
start of the on start loop. 

![add a lives variable](/images/lives_1.png)

### Change the overlap loop for our Enemy @fullscreen
In this game previously the player overlapping with an Enemy would be Game Over with the player losing.
Now let's change to replace the Game Over lose block with a ``||info:change lives by -1 ||`` block

![reduces lives variable](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/lives_2.png)

## Test your game and Next Steps 
### Test your game and Next Steps @unplugged
**This tutorial is now complete.** 

You can test your game to check that each time you touch an enemy your number of lives
goes down by one. 

This tutorial is one of many allowing you add different Game Element on the home page of this Platformer Making Course.
