### @activities true

# Making a Platformer Game Part One

## Introduction 
### Introduction @unplugged

Welcome to part one of this this tutorial on how to make a platformer game with Arcade MakeCode. 
In this tutorial we will cover the basics of how to: 

* Create a Player character
* Move the Player element around the screen
* Create a Game Space using platforms using the tilemap tool
* Add Food to collect using the tilemap tool

## Introduction Creating your Player Character
### Create your Character @fullscreen

To create your character. Drag the  ``||variables:set mySprite||`` ``||sprites:to IMAGE of kind Player||`` into the ``||loops:on start||`` block. 
Click on the blank square and choose a player from the Gallery. What about a duck?
Anything in the ``||loops:on start||``  block runs when the game starts. 

```blocks
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . b 5 5 b . . .
    . . . . . . b b b b b b . . . .
    . . . . . b b 5 5 5 5 5 b . . .
    . b b b b b 5 5 5 5 5 5 5 b . .
    . b d 5 b 5 5 5 5 5 5 5 5 b . .
    . . b 5 5 b 5 d 1 f 5 d 4 f . .
    . . b d 5 5 b 1 f f 5 4 4 c . .
    b b d b 5 5 5 d f b 4 4 4 4 b .
    b d d c d 5 5 b 5 4 4 4 4 4 4 b
    c d d d c c b 5 5 5 5 5 5 5 b .
    c b d d d d d 5 5 5 5 5 5 5 b .
    . c d d d d d d 5 5 5 5 5 d b .
    . . c b d d d d d 5 5 5 b b . .
    . . . c c c c c c c c b b . . .
`, SpriteKind.Player)
```

## Moving your Character
### Move your Character left and right @fullscreen

Drag ``||controller:moveSprite with buttons||`` under your existing block.
Click on the plus sign at the end of the block. Keep ``||controller:vx||`` as 100 but change the  ``||controller:vy||`` setting to 0. 

```blocks
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . b 5 5 b . . .
    . . . . . . b b b b b b . . . .
    . . . . . b b 5 5 5 5 5 b . . .
    . b b b b b 5 5 5 5 5 5 5 b . .
    . b d 5 b 5 5 5 5 5 5 5 5 b . .
    . . b 5 5 b 5 d 1 f 5 d 4 f . .
    . . b d 5 5 b 1 f f 5 4 4 c . .
    b b d b 5 5 5 d f b 4 4 4 4 b .
    b d d c d 5 5 b 5 4 4 4 4 4 4 b
    c d d d c c b 5 5 5 5 5 5 5 b .
    c b d d d d d 5 5 5 5 5 5 5 b .
    . c d d d d d d 5 5 5 5 5 d b .
    . . c b d d d d d 5 5 5 b b . .
    . . . c c c c c c c c b b . . .
`, SpriteKind.Player)
controller.moveSprite(mySprite, 100, 0)
```

### Make our Character Jump @fullscreen

Let's add a **Jump Event** which listens for the ``||controllers:A button||`` being pressed.
When that happens it will move our character up in the y axis. Up here is a negative value. Drag in the ``||controllers: on A button pressed ||``
Drag inside that a block ``||sprites:set mySprite x to 0 ||``. Change ``||sprites:x||`` to ``||sprites:vy velocity||`` set it to **-150**

```blocks
let mySprite: Sprite = null
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    mySprite.vy = -150
})
```

## Change the colour of the background

### Change the colour of the background @fullscreen
Change the colour of your background. Drag in from scene ``||scene:set background color to ||`` after your current blocks and click on the square to choose a colour.

```blocks
scene.setBackgroundColor(9)
```

## What about Gravity?
### What happens? @fullscreen
When we press ``||controllers:A||`` (which is SPACE on the keyboard) we jump but we don't come back down. 
We need gravity! Add another block like ``||sprites:set mySprite x to 0 ||`` to the on start block and change the property to 
``||sprites: ay (acceleration y) ||`` and set that to **300** 

```blocks
let mySprite: Sprite = null
mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . b 5 5 b . . .
    . . . . . . b b b b b b . . . .
    . . . . . b b 5 5 5 5 5 b . . .
    . b b b b b 5 5 5 5 5 5 5 b . .
    . b d 5 b 5 5 5 5 5 5 5 5 b . .
    . . b 5 5 b 5 d 1 f 5 d 4 f . .
    . . b d 5 5 b 1 f f 5 4 4 c . .
    b b d b 5 5 5 d f b 4 4 4 4 b .
    b d d c d 5 5 b 5 4 4 4 4 4 4 b
    c d d d c c b 5 5 5 5 5 5 5 b .
    c b d d d d d 5 5 5 5 5 5 5 b .
    . c d d d d d d 5 5 5 5 5 d b .
    . . c b d d d d d 5 5 5 b b . .
    . . . c c c c c c c c b b . . .
`, SpriteKind.Player)
controller.moveSprite(mySprite, 100, 0)
mySprite.ay = 300
```
## Using Tilemaps
### Create a Floor using a Tilemap @fullscreen

To make a platformer we are going to need a floor and some platforms. 
Drag in the ``||scene:set tilemap to  ||`` block into your on start block. 

```blocks
let mySprite: Sprite = null
mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . b 5 5 b . . .
    . . . . . . b b b b b b . . . .
    . . . . . b b 5 5 5 5 5 b . . .
    . b b b b b 5 5 5 5 5 5 5 b . .
    . b d 5 b 5 5 5 5 5 5 5 5 b . .
    . . b 5 5 b 5 d 1 f 5 d 4 f . .
    . . b d 5 5 b 1 f f 5 4 4 c . .
    b b d b 5 5 5 d f b 4 4 4 4 b .
    b d d c d 5 5 b 5 4 4 4 4 4 4 b
    c d d d c c b 5 5 5 5 5 5 5 b .
    c b d d d d d 5 5 5 5 5 5 5 b .
    . c d d d d d d 5 5 5 5 5 d b .
    . . c b d d d d d 5 5 5 b b . .
    . . . c c c c c c c c b b . . .
`, SpriteKind.Player)
controller.moveSprite(mySprite, 100, 0)
mySprite.ay = 200
tiles.setTilemap(tiles.createTilemap(
            hex`100008000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001010101010101010101010101010101`,
            img`
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2
            `,
            [myTiles.tile0,sprites.castle.tileGrass2,myTiles.tile2],
            TileScale.Sixteen
        ))

```

### Create a Floor using a Tilemap 2 @fullscreen

Click on the square and this opens up the ``||scene:Tilemap||`` editor. 
Change the size in the bottom left to **10 x 8**  because each tile is 16 pixels square this is the just a bit bigger than the size of the screen.
The whole screen is actually **160px wide by 120px high**. You can do the maths if you want :)

![Change size to 10 by 8 ](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/tilemap_1.png)

###Create a Floor using a Tilemap 3 @fullscreen
Create a line of tiles to be a floor. Choose a suitable tile for your floor. Why not the first, default one. Draw a line by clicking tiles at the bottom of the drawing area to create a floor.
Now select the **Wall Drawing tool** and click the same squares. Then click on Done. 

![Create a row of images and walls ](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/makecode-1-2020-02-14-145027.gif)

### Now draw more platforms @fullscreen

Now you will fall and come to rest on the floor. Can also jump up. In fact you can jump a lot, **even when you are in the air!** 
We'll fix that in a bit.  For now **add some more platforms in your tilemap.** 

![Design your platforms ](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/makecode-2.png)

## Jump only when touching floor 
### Jump only when touching floor @fullscreen

To jump only when touching floor we need to add in an extra ``||logic:logic if||`` block in our Event block. 
Drag in a ``||logic:if true then||`` block from the Logic section ``||ControllerButtonEvent: on A button pressed ||``.

```blocks
let mySprite: Sprite = null
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    if (true) {
    	mySprite.vy = -150
    }
})
```

### Jump only when touching floor @fullscreen
Drag in a ``||scene:Scene||`` block ``||scene:is mySprite hitting wall ||`` inside the ``||logic:logic if||`` block. Change the setting to ``||scene:hitting wall bottome||``. 
Now the player will only jump when it is touching down on a platform.  

```blocks
let mySprite: Sprite = null
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    if (mySprite.isHittingTile(CollisionDirection.Bottom)) {
        mySprite.vy = -150
    }

```

## Add a Goal - Collectable Food 

### Adding Food to our Tilemap @fullscreen
**Now we need a Goal for our Game**. 
To add Food for the Player to collect **click on the tilmap image and add in a few yellow squares**. 
In the next step we will then turn them into strawberries.

![Add in Yellow Squares ](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/makecode-yellow-s1-2020-02-16-19.gif)

### Adding Food: Change Squares to Food @fullscreen
Drag a ``||loops: for element value of list||`` block after your current blocks. 
Replace ``||variables:list||`` with ``||scene: array of all locations||`` and choose a yellow block. Inside the ``||for loop||`` add a ``||variables:set strawberry to sprite of kind Food||`` and add a strawberry image from the gallery. 
After this add a ``||scene:place on top of ||`` block and set to ``||scene:place strawberry on top of value||``

![Convert Yellow Squares ](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/makecode-yellow-s2.gif)

### Adding Food: Change Squares to Food @fullscreen

Let's removing the original yellow square which is now behind the strawberry by adding a ``||scene:scene||`` block  ``||scene: set blank box at||``  into our loop. 
Keep the blank image in the first part of the block but change the second value to ``||variables:value||``. 
![blank square](https://github.com/mickfuzz/makecode-platformer-101/blob/master/images/loop_replace_yellow.png?raw=true)


## Eating Food and Points 
### Eating Food and Points  @fullscreen
Drag in a ``||sprites:on sprite of kind Player overlaps ||`` block anywhere on your workspace.
Change the second ``||variables:Player||`` variable to ``||variables:Food||``. 

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
})
```

### Eating Food and Points 2 @fullscreen
Drag in a ``||sprites:destroy mySprite ||`` block inside the ``||sprites:on sprite of kind Player overlaps ||`` block 
Grab the ``||variables:otherSprite||`` variable from the first block onto the ``||variables:mySprite||`` part of the ``||sprites:destroy||`` block

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
    otherSprite.destroy()
})
```

### Eating Food and Points 3  @fullscreen
Add an ``||info:Info||`` block ``||info:change score by 1||`` under the ``||sprites:destroy||`` block
Now Your food should disappear when you touch it and you **gain points**.
```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
    otherSprite.destroy()
    info.changeScoreBy(1)
})
```

## Play Part One
### Play Part One @unplugged

**That's it now let's play our game**

Then play your game to test that it works ok. 

Is it too easy? If so, can you make it changes that so one of the jumps is more challenging? 
Or is it too hard? If so what can you change to make it easier?

Try making small or large changes to the following:

* the jump ``||sprites:vy (velocity y)||``  in the ``||controller:on A button pressed||`` block
* player gravity with the ``||sprites:ay (acceleration y)||`` setting
* player speed left and right in the ``||controller:move mySprite with buttons||`` block
* the location of the platforms to make the jumps more challenging

Get a friend or family member to test it out. Can they collect all the Food first time?
Getting the balance right between too hard and too easy is key to making our game challening and interesting to play. 

Hope you enjoyed part one of this tutorial. In part two we add the following elements to our platform game. 

* Adding an End Goal that you must touch to win game
* Make it so you much collect all Food to win the game
* Creating a larger Game Space by increasing the width of the level
* Adding Levels to extend our Game Space and increase challenge


