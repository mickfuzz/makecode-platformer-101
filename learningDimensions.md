# Learning Dimensions of this Project

This section includes a map of differnt learning dimensions which are possible and likely to emerge from taking part in this 
game making course. It is inspired by the work of Bevan and Petrich around their study of 'tinkering' in science museums, who through
close observation in partnership with learning facilitators mapped some of the complex learning processes which may be 
hard to spot in a quite chaotic and messy learning environment. 

* [Coding Concepts](#coding-concepts)
* [Wider Patterns](#wider-patterns)
* [Design Practices](#design-pratices)
* [21st Century Skills](#21st-century-skills)

## Coding Concepts
These concepts are based on the computational thinking concepts of Brennan and Resnick. They are temporarily paraphrased here and will
be fully rewritten later.

### Sequences
A particular activity or task can be expressed as a series of steps or instructions that can be run by a computer. Like a recipe, a sequence of programming instructions specifies the action that should be happen. The order that taks happen in is significant. Some bugs are due to errors to commands being run in the wrong sequence.

### Data
Data involves storing, retrieving, and updating values. These incude: variables (to contain numbers or strings or images) and lists ( a collection of numbers or strings). Keeping score is a common way to use variables.

### Loops
We could programme an enemy to move 100 pixels to the right, wait 0.2 seconds, and then to repeat the action – moving another 10 steps, and waiting another 0.2 seconds. What if, instead of a single repetition of the action, we want the enemy to move and wait three more times? We could easily add more move and wait blocks. But what if we wanted to repeat the process 100 or 1000 more times? Loops are a way to run the same sequence many times.

### Events
Events – one thing causing another thing to happen – are an essential component of interactive
media. For example, a button triggering the beginning of a music video, or the collision of
two objects causing a game’s player to lose a life.

### Logic
Another key concept in interactive media is logic / conditionals – the ability to make decisions based on
certain conditions, which supports the expression of multiple outcomes. Operators provide support for mathematical, logical, and
string expressions, this commonly used to compare conditions before running code.


## Wider Patterns
### Wider Computing Patterns and Systems Concepts

These wider patterns and concepts are a way to learn about wider computing practices that are also applicable beyond the world of making games. These ideas are common in the area of Interactive Media Design and Systems Thinking.

* [Change Listener](#change-listener)
* [Input Event](#input-event)
* [Separate Formatting from Data](#separate-formatting-from-data)
* [Creating Functions](#creating-functions)
* [Systems Elements](#systems-elements)
* [Systems Dynamics](#systems-dynamics)
* [Balancing Feedback Loops](#balancing-feedback-loops)
* [Reinforcing Feedback Loops](#reinforcing-feedback-loops)

### Change Listener
#### About this Pattern / Concept

* **Name:** Change Listener

* **Description:** Also known as States, this pattern is useful when you want one part of your programme to listen out for changes in the stage of another. An example would be listening for an overlap between the player and an enemy. The programme can then take action when this overlap change happens or a particular condition is true.

* **Why is it needed :** In many media programmes you need to change formatting or to make something happen based on the conditions of other objects.

* **Examples in MakeCode:** Here are one or more examples:
  - listening for the player being in a condition of overlap with an Enemy
  - changing the animation of a player based on if they are still, moving or jumping

### Input Event

#### About this Pattern / Concept

* **Name:** Input Event

* **Description:** Also known as an event handler, this allows do something like use the keyboard or use the mouse and for your programme to do something in response.

* **Why is it needed :** Working with User Input is a key part of most computer programming design, it allows the user to interact with the programme to make things happen.

* **How this happens in MakeCode:** Here are one or more examples:
  - controlling the player movements

### Separate Formatting from Data

#### About this Pattern / Concept

* **Name:** Separate Formatting from Data

* **Description:** Also known more generally as separation of concerns, this is a specific example of the computer programming principle that elements that do different jobs should be apart.

* **Why is it needed :** In many examples this separation allows editors of the project to make changes to the data easily without worrying about the formatting.

* **How this happens in MakeCode:** Here are one or more examples:
    - using tilemaps to represent level layout

### Creating Functions

#### About this Pattern / Concept

* **Name:** Creating Functions

* **Description:** Also known as abstraction and decompostion (by modularisation), this is a pattern that allows programmes to be broken down into smaller pieces, which do a specialist job. In this case the pieces are called functions. 

* **Why is it needed :** The concept is in line with a programming principle called DRY (Don't Repeat Yourself). It allows you to call the same piece of code from different parts of your programme so you don't have to repeat them in more than one place.

* **How this happens in MakeCode:** Here are one or more examples:
      - creating levels on start and when goal is reached

### Systems Elements

#### About this Pattern / Concept
* **Name:** Identifying Systems Elements

* **Description:** This concepts allows you to break down a system into its different parts. In our game we can break down
 the into game components, goal, space, rules and mechanics. This helps to start to identify the different kinds of links
 between the system elements.

* **Why is it needed :** This process of recognising and naming the system elements is the start of being able to understand how a system works.

* **How this happens in our Platformer:** Here are one or more examples:
   - naming the components, rules, space, mechanics and goals of our starting platformer
   - the process of making changes to these game elements

### Systems Dynamics

#### About this Pattern / Concept
* **Name:** Identifying Systems Dynamics

* **Description:** Links between systems elements can be static or dynamic. For example in a game you can have a static number of hazards that never changes, or a dynamic number of enemies that may increase or decrease. The nature of relationship between hazards and player or enemies and player will then be different.

* **Why is it needed :** Recognising dynamic parts of systems allows you to make more informed decisions about how it will change and react to changes. For example understanding these dynamics are important when making a game to make sure the level of challenge for the player is suitable.

* **How this happens in our Platformer:** Here are one or more examples:
      - increasing the number of enemies to increase challenge

### Balancing Feedback Loops

#### About this Pattern / Concept
* **Name:** Balancing Feedback Loops

* **Description:** Feedback loops can be balancing or reinforcing. Balancing feedback loops tend to react to  changes in a system with a responding change that brings balance back.  

* **Why is it needed :** In eco-systems balancing loops work to keep a system stable, preventing there from being too many predators for example, as they will die off if there isn't enough food for them to prey on. In games balance is needed to maintain the right level of challenge for the player.  

* **How this happens in our Platformer:** Here are one or more examples:
      - gravity acting as a balancing force to jump velocity

### Reinforcing Feedback Loops

#### About this Pattern / Concept
* **Name:** Reinforcing Feedback Loops

* **Description:** Feedback loops can be balancing or reinforcing. We can thing of a reinforcing loop as change that gets progressively either bigger or smaller. For example a population of rabbits spiraling larger and larger in a place where they have no natural predators.   

* **Why is it needed :** In a game you may want a reinforcing loop if you want to increase the challenge fo a game. For example, you may want the number of enemies to drastically increase towards the end of a level.

* **How this happens in our Platformer:** Here are one or more examples:
      - creating a hectic game with many spawning enemies



## Design Practices

These concepts are based on the computational thinking concepts of Brennan and Resnick. They also link to the adapted version of Resnick's creative design spiral.

### Goal Setting (decision to add a new mechanic, or change space in a fundamental way)
The process of remxing a game Example activities which demonstrate this incude:
   - Invitation to set new goal or revise existing goals
   - Participant expressing a new goal to include in game or around the wider making experience
   - Clarification or questions on desired design behaviour

### Being incremental and iterative
Designing a project is not a clean, sequential process of first identifying a concept for a project,
then developing a plan for the design, and then implementing the design in code. It is an adaptive
process, one in which the plan might change in response to approaching a solution in small steps.
   - Small revisions to address the game pattern being worked on or sub goals
   - Changes which seeking to maintain or create game balance for suitable challenge level
   - Evaluating aesthetics of graphics / sound elements and revising further

### Debugging
Various testing and debugging practices are possible from learning to scan block code for error messages, to using tools to watch variables. Debugging involves different strategies for dealing with  different kinds of errors including:
   - Glitches - code still works but unexpected result (questioning
   - No errors blank screen, no idea (often retrace steps, go back to earlier version, or have to start again)
   - Clues, greyed out code, red dots, error messages (try to narrow down issue, remove sections of code, again go back, try to find duplication of code blocks)

### Self-Testing and Playtesting
Game testing can be of one's own game or as 'playtesting' of playing each other's game and giving and recieving feedback on game play.
Example activities which demonstrate this incude:
   - Expression of pride, or fun when playing own game
   - Imagining the user's experience of playing their game
   - Giving or receiving feedback either spontaneously or with support form a feedback / playtesting sheet

### Reusing and remixing
Building on other people’s work has been a longstanding practice in programming, and has only
been amplified by network technologies that provide access to a wide range of other people’s
work to reuse and remix.
   - Appropriation without comment or direct copying just taking the idea
   - More direct copying of code via observation or conversation

### Collaborative Production
Where participants work together on game making as pairs or in family groups example activities which demonstrate this incude:
   - Refocusing: redirection back to other participants earlier goals
   - Invitation to imagine the ideal player’s experience
   - Remarks on problematic real behaviour in game play

### Publishing and Evaluating
The process of making work public or sharing a 'finished' version with the group is a key part of the design process and one which can harness key skills of validational and evaluation in a focused way.


## 21st Century Skills
### 21st Century Skills including Digital Literacies

To an extent, in keeping with the broad definitions of 21st Century Skils, this final section is a bit of a catch all to hold some
of the learning skills not covered in previous sections. There are certainly elements of key 21st Century Skills like communication, 
collaboration, critical thinking and creativity are covered the design practices. Certain very specific behaviours especially 
around digital literacies are listed below 
that are well suited to the kind of collaborative and digital game making outlined in this programme. 

NOTE - The are links with 'perspectives' in Brennan and Resink which are more linked to 21st Century Skills. See also Barron's
categorisation of helping behaviours around technology.

### Developing Shared Practices and Vocabulary
The process of working on a joint project involves the development of shared understanding of the problem being worked on. This may involve
checking working concepts by advancing them and questioning meaning of other's expression. This may also include advancing new 
understandings of concepts or processes being worked with.  

* Requesting or offering help in solving problems 

### Joint Problem Solving and Development of Understanding
Closely linked to collaborative production above. Example behaviours include:

* Offering explanation(s) for a strategy, tool, or outcome
* Applying knowledge
* Striving to understand

### Digital Literacies

**Navigating Windows, Tabs and Internet Sites:** 
The detail of moving from one site to another, if especially downloading images from one and then transfering to another gives rise to the 
chance to learn and share a variety of practices which make up key web-navigations literacies. This is an area where young people often are
able to help adults. 

**Logging in and Passwords and Version Control:**
This category is a form of digital literacy which proficient users may take for granted. However for beginner users may need some support with this process.
Often parents as a repository for the logins and passwords of their children as well as encouraging them to save their work.  The way MakeCode doesn't support log ins
encourages a process of saving versions of your work frequently and saving them in a document, say an online google doc with dates and descriptions.

### Notes on Missing elements - TO INTEGRATE
If we look [ at Frameworks here](https://docs.google.com/document/d/1ARce8w_31RXRZ_f5X1HyijJZkaGaX3K8y3QvKkaVgiA/edit#) we can see missing elements around reflection, and expressing elements of understanding (some of which integrated above).

* Social scaffolding
* Development of understanding
