### @activities true

# Getting Started Making a Platformer

##Introduction Creating your Character

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

### What happens? @fullscreen

What happens when we press A (which is SPACE on the keyboard). We jump but we don't come back down. 
We need gravity! To do this we'll use acceleration, again in the y axis, going down, 
Add another block like ``||sprites:set mySprite x to 0 ||`` to the on start block and change the property to 
``||sprites:(ay)acceleration y ||`` and set that to 300

```blocks
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

### Create a Floor using a Tilemap @fullscreen

To make a platformer we are going to need a floor and some platforms. Drag in the ``||scene:set tilemap to  ||`` block into your on start block. 

```blocks
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

### Jump only when touching floor @fullscreen

To jump only when touching floor we need to add in an extra Conditional If block in our Event block. 
Drag in a ``||logic:if True Then||`` block from the Logic section into the on A button pressed Event.

Now drag in a ``||scene:Scene||`` block ``||scene:is mySprite hitting wall ||``  and change the setting to hitting wall bottom. 
Now the player will only jump when it is touching down on a platform.  

```blocks
let mySprite: Sprite = null
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    if (mySprite.isHittingTile(CollisionDirection.Bottom)) {
        mySprite.vy = -150
    }

```

### Add a Goal - Collectable Food

We have some essential pieces of a Game in place. We have a player who can walk left and right and jump when touching the ground. 
We have a space for our player to move it. But we need a Goal for our Game. 
In this next part we are going to add some fruit for our Player to collect. 

### Adding Food to our Tilemap @fullscreen

To add food to collect we are going to add some yellow squares to our tilemap. Later we will then turn them into strawberries.
For now Click on the tilmap image and add in a few yellow squares. See the image tip for visual help to do that. . 

![Add in Yellow Squares ](https://raw.githubusercontent.com/mickfuzz/getting-started-making-a-platformer-test1/master/images/makecode-yellow-s1-2020-02-16-19.gif)

### Adding Food: Change Squares to Food

Now let's create a sprite in the shape of some food. And ask our programme to turn every yellow square into one of those sprites. 


