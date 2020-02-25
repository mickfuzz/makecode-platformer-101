### @activities true

# Making a Platformer Game Part Two

## Adding a End Door 
### Getting Started @unplugged

This is part to of our tutorial on making a Platformer Game. Part One is here. 
In the next screen you will have the relevant blocks to start with. 

 In part two we add the following elements to our platform game. 

* Adding an end goal that you must touch to win game
* Make it so you much collect all Food to win game
* Creating a larger Game Space
* Adding Levels

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

Next we add an **end goal**. When you hit this block you will win (or go to the next level). 
Go into the ``||scene:tilemap||`` and add a brown square where you want your end goal / door to another level to be to be. 
![door in tilemap](https://github.com/mickfuzz/makecode-platformer-101/blob/master/images/door_2.png?raw=true)

### Adding a End Door 2 @fullscreen

To save time we will copy the pattern of adding our Food blocks. Let's duplicate that whole ``||loops:for element value ||`` loop by right clicking it and selecting **Duplicate.**

![blank square](https://github.com/mickfuzz/makecode-platformer-101/blob/master/images/loop_door.png?raw=true)

### Adding a End Door 3 @fullscreen

Drag the duplicated code loop back into your ``||loops:on Start||`` loop under that previous one. And we'll change the  colour to brown, image to a chest, name to chest and the kind to Door. 

![Door loop ](https://github.com/mickfuzz/makecode-platformer-101/blob/master/images/door_3.png?raw=true)


### Adding a End Door 4 @fullscreen

Add a ``||sprites:on sprite of kind Player overlaps ||`` block anywhere on your workspace.
Change the second ``||variables:Player||`` variable to ``||variables:Door||``. 


```blocks
namespace SpriteKind {
    export const Door = SpriteKind.create()
}
sprites.onOverlap(SpriteKind.Player, SpriteKind.Door, function (sprite, otherSprite) {
})
```

### Adding a End Door 5 @fullscreen
Drag in a ``||game: gameOver  ||`` block inside the ``||sprites:on sprite of kind Player overlaps ||`` block 

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
Let's make our game so you have to collect all food before you can end the game. 
Drag a Logic block ``||logic:if true then||`` inside the ``||sprites:on sprite of kind Player overlaps of kind Door ||``
In the new ``||logic:if true then||`` block replace ``||logic:true||`` with at ``||logic:0 = 0 ||`` block from Logic section.

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
We are going to use some new blocks to do with lists called arrays. So to find them type **array** in the search box and press Enter. 
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
To make our game more challenging let's increase the Game Space to create a scrolling game. 
First let's make our Player start on the left of the screen. 
Drag in a ``||sprite:set mySprite position to ||`` under the block setting ``||sprites:acceleration y||``
![game space one](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/game_size_1.png)

### Increase the Game Space 2 @fullscreen
Under that block another one under Scene that says ``||scene:camera follow sprite mySprite||``
![game space one](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/game_size_3.png)

### Increase the Game Space 3 @fullscreen
This new position already gives an idea of the direction of travel. Now click on your ``||scene:tilemap||`` image and change the size to **20 x 8** . 
Click Done and add in new blocks for platforms and food to fill in the new space. 
Remember to add in Walls using the **wall tool**. 
![game space one](https://raw.githubusercontent.com/mickfuzz/makecode-platformer-101/master/images/game_size_2.png)

