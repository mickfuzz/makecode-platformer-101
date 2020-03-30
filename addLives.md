### @activities true


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
            hex`1400080000000000000000000000000000000000000000000400030000000000000000000000000000000000010101030000000000000000000000000000000000000101000000000000000000000000000000000000000000000000000000000000000000000000000000000000000101010100000000000000000000000000000001010000000300000000030000000101010101010101010101010101010101010101`,
            img`
                . . . . . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . . . . . .
                2 2 2 . . . . . . . . . . . . . . . . .
                . . 2 2 . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . . . . . .
                . . . . . . . 2 2 2 2 . . . . . . . . .
                . . . . . . 2 2 . . . . . . . . . . . .
                2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2
            `,
            [myTiles.tile0,sprites.castle.tileGrass2,sprites.builtin.forestTiles0,myTiles.tile1,myTiles.tile2],
            TileScale.Sixteen
        ))
    }
    if (level == 1) {
        tiles.setTilemap(tiles.createTilemap(
            hex`1400080000000000000000000000000000000000000000000400000000000000000000000000000000000000010101030000000000000000000000000000000000000101000000000000000000000000000000000000000000000300000000000000000000000000000000000001010000000000000000000000000000000000000000000000000000000000000000000101010101010101010101010101010101010101`,
            img`
                . . . . . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . . . . . .
                2 2 2 . . . . . . . . . . . . . . . . .
                . . 2 2 . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . . . . . .
                . . . . . 2 2 . . . . . . . . . . . . .
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
sprites.onOverlap(SpriteKind.Player, SpriteKind.Door, function (sprite, otherSprite) {
    if (sprites.allOfKind(SpriteKind.Food).length == 0) {
        level += 1
        mySprite.setPosition(10, 100)
        createLevels()
    }
})
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
    otherSprite.destroy()
})
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    if (mySprite.isHittingTile(CollisionDirection.Bottom)) {
        mySprite.vy = -175
    }
})
function createLevels () {
    chooseLevel()
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
    for (let value2 of tiles.getTilesByType(myTiles.tile2)) {
        chest = sprites.create(img`
            . . b b b b b b b b b b b b . .
            . b e 4 4 4 4 4 4 4 4 4 4 e b .
            b e 4 4 4 4 4 4 4 4 4 4 4 4 e b
            b e 4 4 4 4 4 4 4 4 4 4 4 4 e b
            b e 4 4 4 4 4 4 4 4 4 4 4 4 e b
            b e e 4 4 4 4 4 4 4 4 4 4 e e b
            b e e e e e e e e e e e e e e b
            b e e e e e e e e e e e e e e b
            b b b b b b b d d b b b b b b b
            c b b b b b b c c b b b b b b c
            c c c c c c b c c b c c c c c c
            b e e e e e c b b c e e e e e b
            b e e e e e e e e e e e e e e b
            b c e e e e e e e e e e e e c b
            b b b b b b b b b b b b b b b b
            . b b . . . . . . . . . . b b .
        `, SpriteKind.Door)
        tiles.placeOnTile(chest, value2)
        tiles.setTileAt(value2, myTiles.tile0)
    }
}
let chest: Sprite = null
let strawberry: Sprite = null
let level = 0
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
mySprite.ay = 350
mySprite.setPosition(10, 100)
scene.cameraFollowSprite(mySprite)
scene.setBackgroundColor(9)
level = 0
createLevels()

```

# Remixing a Platformer Game - Add Player Lives

## Adding Player Lives
### Getting Started @unplugged

In this tutorial we will **add player lives** to our platformer.
To do this tutorial you will also need to have done one on *Add an Enemy*.
If you want to understand more about how the starting code of the template works then you can follow [this tutorial](https://arcade.makecode.com/beta#tutorial:https://github.com/mickfuzz/makecode-platformer-101)
 to create the game step by step.

#### About this Game Pattern

This game pattern is one of many you can add to your Platformer in this course.

![mechanics space polish and systems](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/patterns/gamemechanic_extralives_800.png =500x)

*** Name: *** Add Player Lives

*** Description: *** The player starts the game with a number of the lives When the Player is zapped, or runs out of health the play restarts but with one less life.  

*** Need for Pattern: *** Having player lives is a way of reducing the frustration of a challenging game. For example players normally restart from the level they got lost their life on rather than going back to the very beginning.

*** Coding Concepts involved: *** Using Varibles,

*** Links to other Computing Patterns: *** This links to no wider HCI pattern, something about player attributes? Object orientated attributes?


### Adding a starting amount of lives @fullscreen
We can add in the starting number of lives.
To do this drag in from ``||info:info||`` a block  ``||info:set lives to 3 ||`` add this to the
start of the on start loop.

```blocks
info.setLife(3)
```

### Change the overlap loop for our Enemy @fullscreen
In this game previously the player overlapping with an Enemy would be Game Over with the player losing.
Now let's change to replace the Game Over lose block with a ``||info:change lives by -1 ||`` block

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    info.changeLifeBy(-1)
})
```

## Test your game and Next Steps
### Test your game and Next Steps @unplugged
**This tutorial is now complete.**

You can test your game to check that each time you touch an enemy your number of lives
goes down by one.

This tutorial is one of many allowing you add different Game Element on the home page of this Platformer Making Course.
