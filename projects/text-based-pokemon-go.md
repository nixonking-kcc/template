---
layout: project
type: project
image: images/poke-bg.jpg
title: Text-Based Pokemon Go 
# All dates must be YYYY-MM-DD format!
date: 2016-09-23
labels:
  - Java
  - Github
  - Text-Based Simulator
  - Project Assignment
  - JGRASP
summary: My project in ICS 211 that will simulate the Pokemon Go (Text-Based) using Binary Search Tree.
---

<img class="ui large right floated rounded image" src="../images/poke-1.png">
<img class="ui large right floated rounded image" src="../images/poke-2.png">

Have you ever heard of Pokémon Go? Yes, it is an AR mobile game that has become popular since it was released in 2016. In my ICS 211, I had to write a program in java that will simulate the process of how this game actually works. 

In the driver program, it is basically asking the user to catch Pokémon (add Pokémon object), trade Pokémon (remove Pokémon object), or print Pokémon (results). Also, it will terminate/ends the program once the user chooses to quit the game.  The goal of this project is to understand on how to modify the Binary Search Tree (BST) and at the same time, makes other classes which posses different implementations and function for each class (like create nodes, implement all the binary search tree functionality). 

Based on the experience that I had for this project, I have learned a lot from this assignment.  It taught me how actually the binary search trees works, binary tree traversals, recursive method, and a method that will add/remove Pokémon’s objects. Also, it had improved my skills in analyzing and communicating with other students by using GitHub as it was the requirement of this course to be applied in the project.

Here is the code for the driver to test generic class for a binary search tree:

```js
import java.util.*;
public class Pokedex { 
   /** Program that will list the binary search tree for pokemon.
   *@param arg no used
   */  
   public static void main(String [] arg) {
      PokeTree tree = new PokeTree();
      Scanner userIn = new Scanner(System.in);
      String inString = new String("");
      boolean endLoop = false;
   
      //loop until stopping condition is given
      while (!endLoop) { //menu text
         System.out.println("Please enter the number of your choice:");
         System.out.println("1. Catch Pokemon");
         System.out.println("2. Trade Pokemon");
         System.out.println("3. Print Pokedex");
         System.out.println("0. Quit");
         System.out.print("What would you like to do? ");
              
         //read in from user as a String -- much less errors can happen!
         inString = userIn.nextLine();
         
         //take off any spaces on the string
         inString = inString.trim();
        
         //just switch on the String no need to convert to int
         switch(inString) {
            case "0": endLoop = true;
               System.out.println("Good bye!");
               break;
         
            case "1": 
               tree.add(makePokemon());              
               break;
         
         //print out the array for all the Pokemon
            case "2" :
               try {
                  tree.remove(makePokemon());   
               }
               catch (TreeException te) {
                  System.out.print("You have not captured ");
                  System.out.println("this type of pokemon yet");
                  System.out.print("Please catch your Pokemon ");
                  System.out.println("first from number 1\n");
               }       
               break;   
          
          
           //print out the array for all the Pokemon
            case "3" :
               System.out.println(tree);           
               break;  
               
            default: //not a valid menu entry
               System.out.println("\n****Invalid menu choice.****");
               System.out.println("Please enter a 0, 1,2 or 3\n");
               break; 
         } //close switch       
      } //close while
   } //main method

```
