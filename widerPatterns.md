
## Wider Patterns and Concepts

* [Change Listener](#change-listener)
* [Input Event](#input-event)
* [Separate Formatting from Data](#separate-formatting-from-data)
* [Creating Functions](#creating-functions)
* [Systems Elements](#systems-elements)
* [Systems Dynamics](#systems-dynamics)
* [Balancing Feedback Loops](#balancing-feedback-loops)
* [Reinforcing Feedback Loops](#reinforcing-feedback-loops)

These wider patterns and concepts are a way to learn about wider computing practices that are also applicable beyond the world of making games. These ideas are common in the area of Interactive Media Design and Systems Thinking.

## Change Listener

### About this Pattern / Concept

* **Name:** Change Listener

* **Description:** Also known as States, this pattern is useful when you want one part of your programme to listen out for changes in the stage of another. An example would be listening for an overlap between the player and an enemy. The programme can then take action when this overlap change happens or a particular condition is true.

* **Why is it needed :** In many media programmes you need to change formatting or to make something happen based on the conditions of other objects.

* **Examples in MakeCode:** Here are one or more examples:
  - listening for the player being in a condition of overlap with an Enemy
  - changing the animation of a player based on if they are still, moving or jumping

## Input Event

### About this Pattern / Concept

* **Name:** Input Event

* **Description:** Also known as an event handler, this allows do something like use the keyboard or use the mouse and for your programme to do something in response.

* **Why is it needed :** Working with User Input is a key part of most computer programming design, it allows the user to interact with the programme to make things happen.

* **How this happens in MakeCode:** Here are one or more examples:
  - controlling the player movements

## Separate Formatting from Data

### About this Pattern / Concept

* **Name:** Separate Formatting from Data

* **Description:** Also known more generally as separation of concerns, this is a specific example of the computer programming principle that elements that do different jobs should be apart.

* **Why is it needed :** In many examples this separation allows editors of the project to make changes to the data easily without worrying about the formatting.

* **How this happens in MakeCode:** Here are one or more examples:
    - using tilemaps to represent level layout

## Creating Functions

### About this Pattern / Concept

* **Name:** Creating Functions

* **Description:** Also known as abstraction and decompostion (by modularisation), this is a pattern that allows programmes to be broken down into smaller pieces, which do a specialist job. In this case the pieces are called functions. 

* **Why is it needed :** The concept is in line with a programming principle called DRY (Don't Repeat Yourself). It allows you to call the same piece of code from different parts of your programme so you don't have to repeat them in more than one place.

* **How this happens in MakeCode:** Here are one or more examples:
      - creating levels on start and when goal is reached

## Systems Elements

### About this Pattern / Concept
* **Name:** Identifying Systems Elements

* **Description:** This concepts allows you to break down a system into its different parts. In our game we can break down
 the into game components, goal, space, rules and mechanics. This helps to start to identify the different kinds of links
 between the system elements.

* **Why is it needed :** This process of recognising and naming the system elements is the start of being able to understand how a system works.

* **How this happens in our Platformer:** Here are one or more examples:
   - naming the components, rules, space, mechanics and goals of our starting platformer
   - the process of making changes to these game elements

## Systems Dynamics

### About this Pattern / Concept
* **Name:** Identifying Systems Dynamics

* **Description:** Links between systems elements can be static or dynamic. For example in a game you can have a static number of hazards that never changes, or a dynamic number of enemies that may increase or decrease. The nature of relationship between hazards and player or enemies and player will then be different.

* **Why is it needed :** Recognising dynamic parts of systems allows you to make more informed decisions about how it will change and react to changes. For example understanding these dynamics are important when making a game to make sure the level of challenge for the player is suitable.

* **How this happens in our Platformer:** Here are one or more examples:
      - increasing the number of enemies to increase challenge

## Balancing Feedback Loops

### About this Pattern / Concept
* **Name:** Balancing Feedback Loops

* **Description:** Feedback loops can be balancing or reinforcing. Balancing feedback loops tend to react to  changes in a system with a responding change that brings balance back.  

* **Why is it needed :** In eco-systems balancing loops work to keep a system stable, preventing there from being too many predators for example, as they will die off if there isn't enough food for them to prey on. In games balance is needed to maintain the right level of challenge for the player.  

* **How this happens in our Platformer:** Here are one or more examples:
      - gravity acting as a balancing force to jump velocity

## Reinforcing Feedback Loops

### About this Pattern / Concept
* **Name:** Reinforcing Feedback Loops

* **Description:** Feedback loops can be balancing or reinforcing. We can thing of a reinforcing loop as change that gets progressively either bigger or smaller. For example a population of rabbits spiraling larger and larger in a place where they have no natural predators.   

* **Why is it needed :** In a game you may want a reinforcing loop if you want to increase the challenge fo a game. For example, you may want the number of enemies to drastically increase towards the end of a level.

* **How this happens in our Platformer:** Here are one or more examples:
      - creating a hectic game with many spawning enemies
