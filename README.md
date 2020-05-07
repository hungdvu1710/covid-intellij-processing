# processing-projects
## COVID-19 Simulator
The COVID-19 Simulator is based on [this Washington Post simulation](https://www.washingtonpost.com/graphics/2020/world/corona-simulator/). In its current state, it simulates a scenario in which people are social distancing. *This is not meant as a real simulation of COVID-19 transmission, nor should it be taken as medical advice.*

The simulator is largely built off of the [CircleCollision](https://processing.org/examples/circlecollision.html) example by Ira Greenberg.

There are two primary classes:`Ball` and `Column`.

**`Ball`** represents a person in the simulation. It is mostly unchanged from the CircleCollision example, but with the addition of a few instance variables that hold the individual's state (e.g. whether or not they are social distancing, their infected/uninfected/recovered state). 

**`Column`** represents a column of the graph that is above the simulation. It calculates the sizes of the rectangles that make up a column based on the ratio between each of the "types" of people (infected, uninfected, recovered). 

Some ways this example might be improved:
* Logic:
  * Make the simulator take deaths into account.
     - Create boolean var cure
     - If a person is infected and not cured, he'll die
     - If a person is infected and cured, he'll have 60% chance of survival. This will be generated randomly
  * Make the distribution of people be less random; maybe base it off of places people would commonly congregate?
     - Each person will have arrays of possible destination, chosen from set of random places and set of crowd attraction
  * Make infection probabilistic, people shouldn't _always_ be infected if they come in contact with an infected person
     - I'm not sure about the probability of infection, so I'll make it 50/50
  * Add in a variable for mask usage? Or air conditioning? Or airflow?
     - Add boolean attribute protected, If protected, the person will have around 10% chance of infection
* User interface:
  * Allow users to restart the simulator from the interface.
     - Add reset button which invoke reset method that return everything to its beginning state
  * Allow users to change parameters within the simulation from the interface.
     - Then comes the get/set method
* Accessibility:
  * Make this visualization usable for colorblind people. (This part I'll omit since I don't actually know how to
     - Make the balls black and white might do the trick
  * Make this visualization usable for people with limited vision (not sure how friendly Processing is screenreaders! I'd be curious to find out.)
     - Read out loud the number of infected, uninfected, recovered and death?
  

# Using Processing 3 in IntelliJ IDEA

This repository contains an example [Processing 3](https://processing.org) project in [IntelliJ IDEA](https://www.jetbrains.com/idea/).

The project can be used in two steps:

1. Open the project in IntelliJ IDEA
2. Add the same configuration you see on the screenshot
3. Duplicate the example applet and create as many Processing sketches as you want!

![Configuration screenshot](http://cl.ly/image/1b2Q1J2Z1Q1y/processing-intellij.png)

# About

This project contains the Processing core libraries and is therefore distibuted under [GPL licence](LICENSE.md).

*Thank you Processing!*
