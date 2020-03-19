### @activities true

# Making a Platformer Game Part Two

## Adding a End Door 
### Getting Started @unplugged

This is part to of our tutorial on making a Platformer Game. Part One is here. 
In the next screen you will have the relevant blocks to start with. 

 In part two we add the following elements to our platform game. 

* Adding an end goal that you must touch to win game
* Make it so you must collect all Food to win game
* Creating a larger Game Space
* Adding Levels
* Adding a Timer

```template
namespace SpriteKind {
    export const Door = SpriteKind.create()
}
namespace myTiles {
    //% blockIdentity=images._tile
    export const tile0 = img`
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
    `
    //% blockIdentity=images._tile
    export const tile1 = img`
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
    `
}

let strawberry: Sprite = null
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
            hex`0a0008000000000000000000000000000300000000000300010101030000000001010000010100000000000000000000000003000003000000000000010101010000000000000000000001010101010101010101`,
            img`
                . . . . . . . . . .
                . . . . . . . . . .
                2 2 2 . . . . . 2 2
                . . 2 2 . . . . . .
                . . . . . . . . . .
                . . . . . . 2 2 2 2
                . . . . . . . . . .
                2 2 2 2 2 2 2 2 2 2
            `,
            [myTiles.tile0,sprites.castle.tileGrass2,sprites.builtin.forestTiles0,myTiles.tile1],
            TileScale.Sixteen
        ))
scene.setBackgroundColor(9)
for (let value of tiles.getTilesByType(myTiles.tile1)) {
    strawberry = sprites.create(img`
        . . . . . . . 6 . . . . . . . .
        . . . . . . 8 6 6 . . . 6 8 . .
        . . . e e e 8 8 6 6 . 6 7 8 . .
        . . e 2 2 2 2 e 8 6 6 7 6 . . .
        . e 2 2 4 4 2 7 7 7 7 7 8 6 . .
        . e 2 4 4 2 6 7 7 7 6 7 6 8 8 .
        e 2 4 5 2 2 6 7 7 6 2 7 7 6 . .
        e 2 4 4 2 2 6 7 6 2 2 6 7 7 6 .
        e 2 4 2 2 2 6 6 2 2 2 e 7 7 6 .
        e 2 4 2 2 4 2 2 2 4 2 2 e 7 6 .
        e 2 4 2 2 2 2 2 2 2 2 2 e c 6 .
        e 2 2 2 2 2 2 2 4 e 2 e e c . .
        e e 2 e 2 2 4 2 2 e e e c . . .
        e e e e 2 e 2 2 e e e c . . . .
        e e e 2 e e c e c c c . . . . .
        . c c c c c c c . . . . . . . .
    `, SpriteKind.Food)
    tiles.placeOnTile(strawberry, value)
    tiles.setTileAt(value, myTiles.tile0)
}
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
    otherSprite.destroy()
    info.changeScoreBy(1)
})
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    mySprite.vy = -150
})
```

## Adding a End Door 

### Adding a End Goal 1 @fullscreen

Have a look at our starting blocks. We can see ``||controller:Controls||`` our that move our Player and allows them to jump. 
A Platform design and location of Food in our ``||scene:tilemap||``. A ``||loops:loop||`` that creates our food. Finally a ``||sprites:On Event||`` listener removes the food when our player touches it.  

### Adding a End Goal @fullscreen

Next we add an **End Goal**. When you hit this block you will win (or go to the next level). 
Click on the ``||scene:tilemap||`` image and add a brown square where you want your **End goal / Door** to another level to be. 
![door in tilemap](https://github.com/mickfuzz/makecode-platformer-101/blob/master/images/door_2.png?raw=true)

### Adding a End Door 2 @fullscreen

To save time we will copy the **Code Pattern** used to create our Food blocks. Let's duplicate that whole ``||loops:for element value ||`` loop by right clicking it and selecting **Duplicate.**

![blank square](https://github.com/mickfuzz/makecode-platformer-101/blob/master/images/loop_door.png?raw=true)

### Adding a End Door 3 @fullscreen

Drag the duplicated ``||loops:for element||`` loop back into your ``||loops:on Start||`` loop under that previous one. 
Change the ``||scene:locations||`` colour block to brown, change the name to ``||variables:chest||``, the image to a chest and the ``||sprites: of kind||`` value to ``||sprites:Door||``. 
As ``||sprites:Door||`` isn't in the drop-down list, click on **Add new Kind** and enter Door there.  

![Door loop ](https://github.com/mickfuzz/makecode-platformer-101/blob/master/images/door_3.png?raw=true)

### Adding a End Door 4 @fullscreen
Add a ``||sprites:on sprite of kind Player overlaps ||`` block anywhere on your workspace.
Change the second ``||sprites:Player||`` variable to ``||sprites:Door||``. 

```blocks
namespace SpriteKind {
    export const Door = SpriteKind.create()
}
sprites.onOverlap(SpriteKind.Player, SpriteKind.Door, function (sprite, otherSprite) {
})
```

### Adding a End Door 5 @fullscreen
Drag in a ``||game: gameOver  ||`` block inside the ``||sprites:on sprite of kind Player overlaps ||`` block and set it to ``||game:game over WIN||``

```blocks
namespace SpriteKind {
    export const Door = SpriteKind.create()
}
sprites.onOverlap(SpriteKind.Player, SpriteKind.Door, function (sprite, otherSprite) {
    game.over(true)
})
```
## You must Collect all Fruit  
### You must Collect all Fruit 1  @fullscreen
Let's add **challenge** to the game so you must collect all food before you can end the game. 
Drag a Logic block ``||logic:if true then||`` inside the ``||sprites:on sprite of kind Player overlaps of kind Door ||``. 
In the new ``||logic:if true then||`` block replace ``||logic:true||`` with a ``||logic:0 = 0 ||`` block from Logic section.

```blocks
namespace SpriteKind {
    export const Door = SpriteKind.create()
}
sprites.onOverlap(SpriteKind.Player, SpriteKind.Door, function (sprite, otherSprite) {
    if (0 == 0) {
        game.over(true)
    }
})
```

### You must Collect all Fruit 2 @fullscreen
We need new blocks to do with lists called arrays. To find them type **array** in the search box and press Enter. 
Replace the first **0** in the``||logic:0 = 0 ||`` with an ``||arrays:length of array list||`` block.
![array image search](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/all_food_1.png)

### You must Collect all Fruit 2 @fullscreen

Drag the larger ``||variable:set sprite list to array of kind Player||`` into the workspace.
Then replace ``||variable:list||`` in the ``||arrays:length of array ||`` with a ``||sprites:array of kind Player||`` block.
Then change  ``||sprites:array of kind Player||`` to ``||sprites:array of kind Food||``

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Door, function (sprite, otherSprite) {
    if (sprites.allOfKind(SpriteKind.Food).length == 0) {
        game.over(true)
    }
}) 
```
## Increase the Game Space   
### Increase the Game Space 1 @fullscreen
More **challenge**. Let's increase the Game Space to create a scrolling game. 
First let's make our **Player** start on the left of the screen. 
Drag in a ``||sprites:set mySprite position to x 10 y 100 ||`` under the block setting ``||sprites:acceleration y||``
![game space one](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/game_size_1.png)

### Increase the Game Space 2 @fullscreen
Under that block another one under Scene that says ``||scene:camera follow sprite mySprite||``
![game space one](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/game_size_3.png)

### Increase the Game Space 3 @fullscreen
This new position already gives an idea of the direction of travel. Now click on your ``||scene:tilemap||`` image and change the size to **20 x 8** . 
Click **Done** and add in new blocks for platforms and food to fill in the new space. 
Remember to add in Walls using the **Wall Tool**. 
![game space one](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/game_size_2.png)


## Adding another Level  
### Adding another Level 1 @fullscreen

To add another level we are going to move some of our code out of the on start block so we can run it more than once. 
Create a new ``||functions:Function||`` by clicking on the **Advanced** tab on our toolbar, then  ``||functions:Functions||``
And then click **Make a Function**. Enter createLevels in the white box. 
![game level one](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/new_level_1.png)

### Adding another Level 2 @fullscreen
Move the new function next to the bottom part of your ``||loops:on start||`` loop. 
Then move the two ``||loops: for element value||`` loops into the ``||functions: createLevels||`` function. 
Right click and select **Format Code**. Then drag in the ``||functions:call createLevels||`` from ``||functions:Functions||`` to the end of the ``||loops:on start||`` loop. 

![game level two](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/makecode-function-levels1.gif)

### Adding another Level 3 @fullscreen
Under ``||variables:variables||`` make a new variable called level. Then drag the ``||variables: set level to 0||`` 
block towards the end of your on start block but before the ``||functions:call createLevels||`` block. 
![game level three](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/new_level_3.png)

### Adding another Level 4 @fullscreen
Create a new ``||functions:Function||`` by clicking on the **Advanced** tab on our toolbar, then  ``||functions:Functions||``
And then click **Make a Function**. Enter chooseLevel in the white box.


```blocks
function chooseLevel () {
}
```

### Adding another Level 5 @fullscreen
Drag only the  ``||scene:set tilemap to||`` into the new ``||functions:chooseLevel||`` function by holding down **Control** on your Keyboard while you drag the block. 
Right click and select **Format Code** to make the screen tidy. 
```blocks
namespace myTiles {
    //% blockIdentity=images._tile
    export const tile0 = img`
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
    `
    //% blockIdentity=images._tile
    export const tile1 = img`
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
    `
    //% blockIdentity=images._tile
    export const tile2 = img`
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
    `
}
function chooseLevel () {
    tiles.setTilemap(tiles.createTilemap(
            hex`1400080000000000000000000000000000030000000000000400030000000000030000000101000000000000010101030000000001010000000000000000000300000101000000000000000000000000000101010000000000000300000300000000030000000000000000000000010101010000000001010000000000000000000000000000000300000000030000000101010101010101010101010101010101010101`,
            img`
                . . . . . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . 2 2 . . . . . .
                2 2 2 . . . . . 2 2 . . . . . . . . . .
                . . 2 2 . . . . . . . . . . . . . 2 2 2
                . . . . . . . . . . . . . . . . . . . .
                . . . . . . 2 2 2 2 . . . . 2 2 . . . .
                . . . . . . . . . . . . . . . . . . . .
                2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2
            `,
            [myTiles.tile0,sprites.castle.tileGrass2,sprites.builtin.forestTiles0,myTiles.tile1,myTiles.tile2],
            TileScale.Sixteen
        ))
}
```

### Adding another Level 6 @fullscreen
Drag in the ``||functions:call chooseLevel||`` from ``||functions:Functions||`` to the end of the begining of the ``||functions:createLevel||`` function. 

![game level four](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/new_level_4.png)

### Adding another Level 7 @fullscreen
Now add a Logic block ``||logic:if true then||`` inside the ``||sprites:chooseLevel ||`` block
Move the the ``||scene:set tilemap to||``  inside the logic block.
In the new ``||logic:if true then||`` block replace ``||logic:true||`` with at ``||logic:0 = 0 ||`` block from Logic section.

```blocks
namespace myTiles {
    //% blockIdentity=images._tile
    export const tile0 = img`
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
    `
    //% blockIdentity=images._tile
    export const tile1 = img`
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
    `
    //% blockIdentity=images._tile
    export const tile2 = img`
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
    `
}
function chooseLevel () {
    if (level == 0) {
        tiles.setTilemap(tiles.createTilemap(
            hex`1400080000000000000000000000000000030000000000000400030000000000030000000101000000000000010101030000000001010000000000000000000300000101000000000000000000000000000101010000000000000300000300000000030000000000000000000000010101010000000001010000000000000000000000000000000300000000030000000101010101010101010101010101010101010101`,
            img`
                . . . . . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . 2 2 . . . . . .
                2 2 2 . . . . . 2 2 . . . . . . . . . .
                . . 2 2 . . . . . . . . . . . . . 2 2 2
                . . . . . . . . . . . . . . . . . . . .
                . . . . . . 2 2 2 2 . . . . 2 2 . . . .
                . . . . . . . . . . . . . . . . . . . .
                2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2
            `,
            [myTiles.tile0,sprites.castle.tileGrass2,sprites.builtin.forestTiles0,myTiles.tile1,myTiles.tile2],
            TileScale.Sixteen
        ))
    }
}
```

### Adding another Level 8 @fullscreen
Right click on the Logic block ``||logic:if level = 0 ||`` and duplicate it. 
Change 0 to 1 in the second block and drag it back into the ``||functions:chooseLevel||`` function. 

```blocks
namespace myTiles {
    //% blockIdentity=images._tile
    export const tile0 = img`
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
    `
    //% blockIdentity=images._tile
    export const tile1 = img`
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
    `
    //% blockIdentity=images._tile
    export const tile2 = img`
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
    `
}
function chooseLevel () {
    if (level == 0) {
        tiles.setTilemap(tiles.createTilemap(
            hex`1400080000000000000000000000000000030000000000000400030000000000030000000101000000000000010101030000000001010000000000000000000300000101000000000000000000000000000101010000000000000300000300000000030000000000000000000000010101010000000001010000000000000000000000000000000300000000030000000101010101010101010101010101010101010101`,
            img`
                . . . . . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . 2 2 . . . . . .
                2 2 2 . . . . . 2 2 . . . . . . . . . .
                . . 2 2 . . . . . . . . . . . . . 2 2 2
                . . . . . . . . . . . . . . . . . . . .
                . . . . . . 2 2 2 2 . . . . 2 2 . . . .
                . . . . . . . . . . . . . . . . . . . .
                2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2
            `,
            [myTiles.tile0,sprites.castle.tileGrass2,sprites.builtin.forestTiles0,myTiles.tile1,myTiles.tile2],
            TileScale.Sixteen
        ))
    }
    if (level == 1) {
        tiles.setTilemap(tiles.createTilemap(
            hex`1400080000000000000000000000000000030000000000000400030000000000030000000101000000000000010101030000000001010000000000000000000300000101000000000000000000000000000101010000000000000300000300000000030000000000000000000000010101010000000001010000000000000000000000000000000300000000030000000101010101010101010101010101010101010101`,
            img`
                . . . . . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . 2 2 . . . . . .
                2 2 2 . . . . . 2 2 . . . . . . . . . .
                . . 2 2 . . . . . . . . . . . . . 2 2 2
                . . . . . . . . . . . . . . . . . . . .
                . . . . . . 2 2 2 2 . . . . 2 2 . . . .
                . . . . . . . . . . . . . . . . . . . .
                2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2
            `,
            [myTiles.tile0,sprites.castle.tileGrass2,sprites.builtin.forestTiles0,myTiles.tile1,myTiles.tile2],
            TileScale.Sixteen
        ))
    }
}
```

### Adding another Level 9 @fullscreen
Repeat the process again  changing the ``||varaiables:level||`` number  to two. 
Move your ``||game:game over||`` win block into and delete the ``||scene:tilemap||`` block.  

```blocks
namespace myTiles {
    //% blockIdentity=images._tile
    export const tile0 = img`
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
    `
    //% blockIdentity=images._tile
    export const tile1 = img`
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
    `
    //% blockIdentity=images._tile
    export const tile2 = img`
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
        4 4 4 4 4 4 4 4 4 4 4 4 4 4 4 4
    `
}
function chooseLevel () {
    if (level == 0) {
        tiles.setTilemap(tiles.createTilemap(
            hex`1400080000000000000000000000000000030000000000000400030000000000030000000101000000000000010101030000000001010000000000000000000300000101000000000000000000000000000101010000000000000300000300000000030000000000000000000000010101010000000001010000000000000000000000000000000300000000030000000101010101010101010101010101010101010101`,
            img`
                . . . . . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . 2 2 . . . . . .
                2 2 2 . . . . . 2 2 . . . . . . . . . .
                . . 2 2 . . . . . . . . . . . . . 2 2 2
                . . . . . . . . . . . . . . . . . . . .
                . . . . . . 2 2 2 2 . . . . 2 2 . . . .
                . . . . . . . . . . . . . . . . . . . .
                2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2
            `,
            [myTiles.tile0,sprites.castle.tileGrass2,sprites.builtin.forestTiles0,myTiles.tile1,myTiles.tile2],
            TileScale.Sixteen
        ))
    }
    if (level == 1) {
        tiles.setTilemap(tiles.createTilemap(
            hex`1400080000000000000000000000000000030000000000000400030000000000030000000101000000000000010101030000000001010000000000000000000300000101000000000000000000000000000101010000000000000300000300000000030000000000000000000000010101010000000001010000000000000000000000000000000300000000030000000101010101010101010101010101010101010101`,
            img`
                . . . . . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . 2 2 . . . . . .
                2 2 2 . . . . . 2 2 . . . . . . . . . .
                . . 2 2 . . . . . . . . . . . . . 2 2 2
                . . . . . . . . . . . . . . . . . . . .
                . . . . . . 2 2 2 2 . . . . 2 2 . . . .
                . . . . . . . . . . . . . . . . . . . .
                2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2
            `,
            [myTiles.tile0,sprites.castle.tileGrass2,sprites.builtin.forestTiles0,myTiles.tile1,myTiles.tile2],
            TileScale.Sixteen
        ))
    }
    if (level == 2) {
        game.over(true)
    }
}
```

### Adding another Level 10 @fullscreen
In the ``||sprites:on sprite of kind Player overlaps Door ||`` event block add a ``||variables:change level by 1||`` block. 
Next add a ``||sprites:set mySprite position to x 10 y 100 ||``
Then add a ``||functions:createLevels||`` block from ``||functions:Functions||``

![game level four](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/new_level_4.png)

## Add a Timer
### Add a Timer @fullscreen

To add more **challenge** to our game the final thing we will do is add a timer for each level. 
Drag from ``||info:Info||`` a ``||info:start countdown ||`` block to the start of the ``||functions:createLevels||`` function.

![game timer](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/timer_1.png)


## End Notes
### End Notes @unplugged

**Congratulations - Now Play your Game**

Then play your game to test that it works ok. And get someone else to test it too.

Is it too easy? Or is it too hard? If so what can you change to make it easier or harder?
Try making small or large changes to the following:

* Location of the **Platforms** and your **Food** and **End Goal**
* **Game Space** size
* **Timer** settings
* Number of **Food** items

Now you have the core of your game in place you can add more to it. 
How about the following 

* Add Enemies
* Add Moving Enemies
* Add Music and Sound Effects
* Add Animations to make your Player come alive
* Double Jump
* Add instructions and comments
* Jump on Enemies to zap them

There are follow-up tutorials to come but for the meantime just have a play. 
