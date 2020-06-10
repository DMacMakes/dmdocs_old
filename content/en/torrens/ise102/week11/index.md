---
title: "Week 11: Objects 2"
linkTitle: "W.11: Objects 2"
weight: "110"
description: >
  How do we check if things collide? How can we use bunches of related objects easily? How do we add more screens to our game?
---

## Homework:

To wrap around, or teleport to the other side of the garden:
* Move _Batty_ each frame
* When a move takes her onto a pixel that's out of bounds, **manually change her x,y location** to a safe pixel on the other side of the screen.
* If that's not clear, here's a visual:

{{< imgcard edge_teleport_explained>}}
Edge teleport: When Batty's somewhere bad, (B1) put her somewhere that isn't (B2).
{{< /imgcard >}}



## More Screens

To **add features** we'll need more screens. _Game Over_, _Menu_, _Set Difficulty_ etc. I've provided code to get started.

Run it, try to **break it** and **extend it before you begin to integrate it** with your own code. Once it's mixed up with something else you'll be stuck with any assumptions you didn't test, and it takes advanced debugging to correct.

 <a class="btn btn-lg btn-primary mr-3 mb-4" href="Week11_Screens.zip" target="_blank">Download Week11_Screens.zip<i class="fas fa-arrow-alt-circle-right ml-2"></i></a>

{{< alert title="Learn Code Before Adding" color= "danger" >}}
**Integrate code before you've genuinely understood it and you _will_ come undone.** 

Usually near the end.
{{< /alert >}}
 
 {{< imgcard screens_all3 >}}
 {{< /imgcard >}}
 
### The Code Summary

A `screen` is a just a name I chose for what part of the game we're in. The _menu screen_, or the _play screen_.

I made a `screen` variable in `main()` and then, in loop, I check it and display the right screen. 
* The loop isn't 60fps like the drawing loops
* It calls a function, to show a screen and doesn't resume until the player leaves that screen

{{< imgcard code_screens_summary Link "code_screens_summary.png">}}
{{< /imgcard >}}

 
### The Menu
 
 Open the solution, and let's look through the menu.
 
 * **Q)** How is a menu screen different to a game screen? 
 * **A)** It isn't.
 * Just have a draw loop like `playSnake()` does.
   * display choices on screen with a string drawing function
   * Wait for a button press
   * Return the new screen id back to main.
 
In main: If `screen==MENU` call `showMenu()` instead of `playSnake()`.

{{< imgcard code_showMenu Link "code_showMenu.jpg">}}
Drawing and getting input is easy. The important job is to store the user's `choice` and send it back to `main`.
{{< /imgcard >}}

## More Collisions

We already know how to check if Batty collides with a wall (check her location and the wall location), it should be super easy to check if we've hit other stuff.

### Adding Other Stuff

Fruit are things our Snake/Bat can eat by running into them. They don't have many properties: maybe a location (x, y), a colour and what kind fruit they are. 

```cpp
Fruit anApple;
apple.x = apple.y = 15;
apple.colour = FG_GREEN;
apple.kind = "apple"
```

* If we have a fruit with a location we can check if Batty is on the same pixel.
* Then we could move the fruit to a new random location.

We don't have a Fruit data type though..

### Exercise 1: Define And Add Fruit

You know that Creature is defined somehow in `creature.h`. Some of you might have even looked.

1. Open your solution's folder in explorer.
2. Copy and Paste `creature.h`.
3. Rename the copy `fruit.h`
4. Open it up and see if you can change it from a `Creature` to a `Fruit`.
  - Give it the right class name.
  - Add the `kind` variable to it.
  - Get rid of xDir and yDir, since Fruit doesn't move around.
5. Add an `Apple` to `playBattyGame()`, like you added a Creature. Remember to draw it too, just like batty..

{{< imgcard code_creature_h >}}
Creature.h
{{< /imgcard >}}

### Colliding With Fruit

You know how to collide with a wall: checking if a wall pixel is located where the bat pixel is located.
Fruit's the same: This is pseudocode for what we've done, plus fruit:

```
function int playBattyGame
  create batty
  create fruit
  place batty and fruit in some position

  while player hasnt quit
    listen for inputs
    if we want to move this frame:
      move batty 1 pixel in his current direction
      if batty x is same as a wall x or batty is is same as a wall y:
        Move batty to a safe pixel on other side.
      end if
      if batty x and y match the fruit's x and y:
        Increase player score
        Give the fruit a new location
      end if
    end if
  end while
} // end of playBattyGame
```



### Exercise: Collide with fruit
Most of the code above, we've already done. I've just converted it back into English/pseudocode, to help you remember the steps we're taking, without getting thrown by code.

Now, take those steps and turn them into code!

### Exercise: Adding To The Score

The score is just a variable we can keep in battyGamePlay/snakeGamePlay. 

To show it on the screen, you can use drawString as long as you convert your score to a string. Use `drawString` and use `to_string(myInt)` to convert your int to a string.

```cpp
  /// Draw a normal (not wide) string to x,y
  drawString(xLocation, yLocation, stringIWantToWrite);
  
  /// To set both foreground and background colours of your text:
  drawString(xLocation, yLocation, stringIWantToWrite, layerColour(FG_WHITE, BG_DARK_RED) );
  
  /// Use to_string() to convert an int to a string. drawString won't take numbers directly 
  drawString(xLocation, yLocation, to_string(myInteger) );
  
  /// Join strings and numbers
  /// Use to_string() to convert an int to a string. drawString won't take numbers directly 
  int age = 20;
  drawString(xLocation, yLocation, "Age: " + to_string(age) );
```

Remember, you also have `drawWString` if you want to use Unicode, and `to_wstring` to convert `int` to `wstring``.

## Wing-spreading Time

{{< imgcard big_baby_bird>}}
Dad needs you to open those wings mate.
{{< /imgcard >}}

It's that time boys and girls. From here on my explanations and source code get less direct. 
I'll give you examples,pseudocode and help, but you have to do work out how to put it together yourself now.

### Looking It Up Yourself

1) Learn what you've put off: `for` and `while`  loops, functions, `switch` statements: if you're not sure, do the googling and the reading now.
2) Learn the range of sites that can help you, each with their own style: _geeksforgeeks_, _stackoverflow_, _Wikpedia_, _cppreference_ and _youtube_. If you take responsibility for learning, for being curious and active, these sites will see you there. 
  * Detailed but not a reference sheet: https://www.geeksforgeeks.org/switch-statement-cc/
  * Listicle style: https://www.geeksforgeeks.org/interesting-facts-about-switch-statement-in-c/
  * Across languages, high level view: https://en.wikipedia.org/wiki/Switch_statement
  * Question and answer: https://stackoverflow.com/questions/31410393/c-switch-cases/31410441
  * Technical, authoritative: https://en.cppreference.com/w/cpp/language/switch

### Don't Push Code Around

"Don't push paint around" is a phrase art teachers use to counter something they, us, and everyone else does. When we have gone beyond our understanding, but we know we're kinda close, we start to noodle and try random stuff. In concept art it's maybe because we don't really know how to paint folds in fabric, or how to render realistic hair. We don't have reference photos for combat armour, or we never figured out the perspective properly.

You're new to coding, and you'll often have bugs that come from misunderstanding c++ syntax, its basic structures. When that happens, it'll feel like you're close, but you'll never get there: reordering, changing variable values, none of it's working because you don't actually know how to do a comparison in your `while` statement, or that you have to store the value a function is returning.

What you need to do is solve the underlying problem, outside of your program, and come back with the knowledge.

{{< alert title="(A) Golden Rule: Work Small To Big" color= "primary" >}}
Test small chunks of code in isolation and you'll be able to focus down the problem. Students often spend hours and days trying to fix their logic, despite knowing they're kind of winging it on functions or the difference between `&&` and `||`. Maybe they can just get this one thing solved and not have to dig into that.

Take the two or three lines you _know_ you don't really understand and put them in `main()` in a new, empty project. Throw in some dummy values, try to ask new questions in that new lightSee them without anything around them, think about what you're assuming about the c++ keywords/operators/syntax in that code and how you can test if you're right. 
{{< /alert >}}


  
### Add More?

You can create all sorts of game elements now.
1. Decide their properties
2. Make a definition (class) for their object
3. Give them a location and draw them
4. Check if batty runs into them
5. Code what happens next

You can add deadly obstacles like FlameBlocks or MetalSpikes that end the game. Fruit that changes your speed more than usual. Rotten fruit that costs you points.

{{< alert title="The Golden Rule" color= "primary" >}}
A player should never have to guess what happened.

If they hit a rotten fruit, you have to make clear it was rotten fruit, and what penalty was paid.
* Changing the top or bottom border to display "ROTTEN APPLE: -3 SCORE" for 2 seconds is one possible way.
  * You could tutorialise it a bit by pausing the game for 2 seconds the first time it happens, so they def read the message.
{{< /alert >}}

## Vectors Hold Your Collections
 
 Want to make 10 of something, or 100? Without dealing with 100 variable names?
 
 The _vector_ is an object that can hold those for you. 
 
 {{< alert title="Indexed Collections" color= "primary" >}}
 A gallery contains lots of precious and small items. When you visit with your family then, you're not surprised that they don't want people taking in bags: they ask you to leave yours with security in the `bag check`. It's full of all different sizes and shapes of bags, and when they take yours they assign it a number so they can find it again.
 
 When you've had your walk around the gallery you return and fish out the piece of paper with your bag's assigned number. Without needing any sort of description, they find and return your bag.
 {{< /alert >}}
 
 You create a single vector object, and can submit as many objects to it as you like for safe keeping. To access any object, just provide an _index_. Like with most indices in c++, it starts at 0.

### Vector Of Fruit

In English, what we'll do:
1. Make some fruits, give them location, kind, and colour
2. Draw them all to screen

More c++ specific:
1. Creating and initialise multiple fruits (no need for loop)
2. Drawing those fruits with a regular `for` loop.



### Bonus: `for_each`
3. Drawing those fruits with a `for_each` to reduce bugs

## Intermediate Level: Moving The Collision Code

`playBattyGame()` is getting bloated with wall collision code, then fruit collision code. Long functions are tough to read and debug.
Can we **move that stuff into a function?**.

x and y are two values, so we can't assign a return value. It'd be great to pass batty to to a function and have it change the positions. Functions work on a value copy of our object though, not the original. We need a solution.. 

### Have Functions Return Collision Results

When Batty collides with Fruit, we can return the Fruit or null, a single return value (object). When Batty hits a wall it's more complicated because we need new values for x and y, and we don't have an object that holds them.

Here are three techniques, in order of complexity:
1. Just check one dimension: up and down OR left and right.
2. Return an object containing x and y values.
3. Return a vector with two ints, the x and y direction.
4. Pass batty _by reference_ and have the function edit her directly. Point2D, wh

### 1. One Dimension

Consider a function that takes batty's x position and x direction (or batty herself) then returns the new x position. It would work just as well for y, since screenWidth and screenHeight are th same.

```cpp  
Psuedocode:
 if batty is moving horizontally
   batty's x should equal the output of teleportIfOOB( batty's x, batty's x direction)
 else 
   do the same thing but with her y and y direction
 endif 
 
 function teleportIfOOB( int position, int direction)
   int newPosition = position 
   
   if travelling positive 
    if past highest in bounds value
      newPosition = lowest in bounds value
    endif
   else 
    Do the lower bounds test this time
   endif
   
   return newPosition
 end teleportIfOOB
```  

### 2. A 2D Coordinate Object

If we could return an object that holds x,y coordinates, then we can pass in batty's `x`, `y`, `xDir` and `yDir`) and use the resulting `x,y` object to set her new direction.
Create a new object type that holds x and y values: XYPair, or Coordinates, or Point2D, whatever makes sense to you.

1. Declare XYPair teleportedPosition;
2. Pass Batty or the values above, to a function that returns the new x,y position as an XYPair, assign the returned value to XYPair.
2. Set Batty's x to teleportedPosition.x, same for y.

### 3. Pass By Reference (Intermediate Level)

Normally a function passes a variable's value as a copy, we can't change the original. There _is_ actually a way _C++_ to pass a reference to the original variable (albeit with a different name), letting us edit the original.

This would let us pass in `batty`, and the function will directly change her `x` and `y` if she's out of bounds.

* In the function declaration add `&` to the name of the argument variable: `bool teleportIfOOB(Creature &thatCreature)`
* If you pass `batty` to that function, changes to `thatCreature` in the function are really changes to batty.
* It doesn't need to `return` anything since original `batty` has been changed.
* It leaves us with a knowledge gap.. Was Batty teleported? Why not have the function `return` a `true`/`false` for that outcome?
```cpp
// Teleport if out of bounds
bool teleportIfOOB(Creature &thatCreature )     // versus (Creature batty)
{
  bool teleported = false;
  // Just modifying values for demonstration
  if ( /* test here for x out of bounds..*/ )
  {
    thatCreature.x = /* new in bounds x position goes here */
    teleported = true;
  }
  /* Do the y test */
  return (teleported);
  
}

void play()
{
  batty.x = 50;
  bool battyTeleported = teleportIfOOB(batty);
  
}
```
References are a bit like nicknames are for your friends. Your friend's mother might call her **Sherry**, but she'll answer to **NoHeelzNoFeelz** in a raid. 

#### Aren't References Messing Up Our Rules?

We had learned that functions only use value copies and have no direct access other function's variables.
* It was nice and clear cut..
* but it was, in reality, a simplification to make learning easier
* Yes it does complicate our rules, increasing cognitive load, even potentially confusing us.

Powerful **new features come at the cost of clarity**, and often trade cognitive load for brevity and new possibilities.

#### So Is It Worth It

Yeah, in the same way adulthood is worth it. The rules get murkier and more confusing, but you can do a lot more.

* References super useful when objects get big, and save a lot of processing and memory. 
* That's critical for game performance. 
* They save on a lot of globals and extra awkward function calls.
* They let us make our game worlds bigger and more interesting.

## Homework

Do the fruit collision work if you didn't get it done in class. Send me a zip in the next 2 days, along with any questions.

Then: Push on with assessment! You have fruit, collisions, teleporting, scoring.. 

**I won't be spelling out** for you what **exact bit to do as homework**: this stuff just needs doing. I'll be mostly teaching about vectors(collections) and snake movement options in a short class next week. You want to have your game modes and screens started/finished by then, so you have time left to try adding the segmented snake body.

**What's left?**

### Game Over!
A way to **end the game**. There's work to be done like:
* showing a game over message/screen
* making it obvious to the person where they died and why,
* and letting them know their final score
* letting people go to the menu or play again.
* 
We have no way of dying right now, but we want that screen sorted, so we have **a couple choices**:
1) **Make our snake grow** and eat itself
   - That's a _lot_ of work getting the snake to grow and move
   - There's also plenty of testing self-collision/self-biting before we can test something as simple as game over
   - It'll be hard to tell snake body problems end and game over screen problems start.
2) Temporarily make the walls deadly again.
   - It's easy: we already collide with the wall. Instead of moving the snake, turn it blood red and say game over.
   - That totally doubles as a mode you could put in the main menu. Play Snake and Play Snake (electric fence)
3) Make a DeathBlock or Shredder object, like you made Fruit. Put it on screen, and end the game if your snake hits it.
   * Also easy
   * Also a game mode or game option 
   * Maybe it's a progressive difficulty thing.
  
### Game Modes

To get more than a pass/credit, you want to have extra features and options in the game. See my ideas in _game over_, the ideas in the pdf brief, also just think of fun ideas.
  