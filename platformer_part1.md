### @activities true

# Making a Platformer Game Part One

## Introduction Creating your Character

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

To make our character jump we will need to add an Event. This event will listen for the a button being pressed.
When that happens it will do something. In this case move our character up in the y axis. Up here is a negative value.  
Drag in the ``||ControllerButtonEvent: on A button pressed ||``
An inside that event drag in the block that looks like  ``||sprites:set mySprite x to 0 ||`` and change x to vy velocity and set it to 150

```blocks
let mySprite: Sprite = null
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    mySprite.vy = -150
})
```
## What about Gravity?
### What happens? @fullscreen

What happens when we press A (which is SPACE on the keyboard). We jump but we don't come back down. 
We need gravity! To do this we'll use acceleration, again in the y axis, going down, 
Add another block like ``||sprites:set mySprite x to 0 ||`` to the on start block and change the property to 
``||sprites:(ay)acceleration y ||`` and set that to 300

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

To make a platformer we are going to need a floor and some platforms. Drag in the ``||scene:set tilemap to  ||`` block into your on start block. 

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
Change the size in the bottom left to 10 x 8 which is the size of the screen. 
Then draw a line on the bottom row. 

![Change size to 10 by 8 ](https://p33.f1.n0.cdn.getcloudapp.com/items/4gumAoNv/Screenshot-2020-02-14T14%3A43%3A16.659Z.png)

###Create a Floor using a Tilemap 3 @fullscreen

Select a suitable tile for your floor. Why not the first, default one. Draw a line at the bottom of your area to create a floor.
Then select the Wall drawing tools and select the same squares. Click on Done. 

![Create a row of images and walls ](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/makecode-1-2020-02-14-145027.gif)

### Now draw more platforms @fullscreen

If this works then you should come to rest on the floor and should able to jump up. In fact you can jump a lot. 
We'll fix that in a bit but for now add some more platforms in your tilemap. 

![Design your platforms ](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/makecode-2.png)

## Change the colour of the background

### Change the colour of the background @fullscreen
Change the colour of your background. Drage in from Scene ``||scene:set background color to ||`` after your current blocks and click on the square to choose a colour.

```blocks
scene.setBackgroundColor(9)
```

## Jump only when touching floor 
### Jump only when touching floor @fullscreen

To jump only when touching floor we need to add in an extra Conditional If block in our Event block. 
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
Now drag in a ``||scene:Scene||`` block ``||scene:is mySprite hitting wall ||``  and change the setting to hitting wall bottom. 
Now the player will only jump when it is touching down on a platform.  

```blocks
let mySprite: Sprite = null
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    if (mySprite.isHittingTile(CollisionDirection.Bottom)) {
        mySprite.vy = -150
    }

```

## Add a Goal - Collectable Food 
### Add a Goal - Collectable Food 

We have some essential components of a **Game** in place. We have a player who can walk left and right and jump when touching the ground. 
We have a **Space** for our player to move it. **Now we need a Goal for our Game**. 
In this next part we are going to add some fruit for our Player to collect. 

### Adding Food to our Tilemap @fullscreen

To add food to collect we are going to add some yellow squares to our tilemap. Later we will then turn them into strawberries.
For now **Click on the tilmap image and add in a few yellow squares**. 

![Add in Yellow Squares ](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/makecode-yellow-s1-2020-02-16-19.gif)

### Adding Food: Change Squares to Food @fullscreen

Now let's create a sprite in the shape of some food. And ask our programme to turn every yellow square into one of those sprites. 

![Convert Yellow Squares ](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/makecode-yellow-s2.gif)

### Adding Food: Change Squares to Food @fullscreen

Let's tidy this up by removing the original yellow square so it doesn't get confusing. 
Do this by adding a block  ``||scene: set blank box at||`` from Scene into our loop. 
![blank square one](https://github.com/mickfuzz/makecode-platformer-101/blob/master/images/loop_replace_yellow_1.png?raw=true)


### Adding Food: Change Squares to Food @fullscreen

Keep the blank image in the first part of the block but change the second value to value. You can drag it in from the one above. 
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
When playing your game now. Your food should disappear when you touch it and you gain points.
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

Hope you enjoyed part one of this tutorial. In part two we add the following elements to our platform game. 

* Adding an end goal that you must touch to win game
* Make it so you much collect all Food to win game
* Creating a larger Game Space
* Adding Levels

