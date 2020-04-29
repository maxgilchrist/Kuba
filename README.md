# Kuba
Max Gilchrist, Kevin Li
Gamescrafters Theory Team

## SP 20 Write Up 
Here are two references to the Kuba game and instructions:
[Rules 1](http://www.di.fc.ul.pt/~jpn/gv/kuba.htm)
[Rules 2](https://sites.google.com/site/boardandpieces/list-of-games/kuba)

### Board Count
We broke down the board into three possible cases: (1) all possible positions with at least one white and one black marble, (2) all winning board positions for white with no black marbles, and (3) all winning board positions for black with no white marbles. 

Case 1: ![case1]()

Case 2: ![case2]()

Case 3: ![case3]()

The total sum was 1.24E26.

### Smaller Possibilities
Given that our count was too large, we experimented with three smaller, 5x5 versions of the game.

![225]()![2213]()![885]()

We found that the 5x5 board with 2 starting whites/blacks and 5 reds best maintained the overall strategic features of the original game.

### Tier Count for 2,2,5
| Tier   | Pieces        | Number     |
| ------ |:-------------:| ----------:|
| 0      | r=5, w=2, b=2 |       |

### For the future


### Goal
My goal is to the create the tighest hash possible 
for any solving of the game

### Overview
The end goal is to create a triple tier hash dictonary
the way at the end the API for this structure
should addPosition(position) lookup(position)
The triple tiered dictonary is comprised of 
three layers. 
**First Layer** - Counts red and returns pointer to correct second layer
**Second Layer** - Counts white and returns point to correct third layer
**Third Layer** - Counts black and returns point to the correct hashmap

As we already have an upperbound on the number of positions in each tier
we have intialized all of the hashmaps with that size and this 
gurantees that our load factor = (n/k) < 1 where n is the number of entries
and k is the number of bucks. 

### Symmerties
We can use symmetries in order to lower the entries in each table. Once, we have
computed the actual tree once we have a precise value of k such that n = k for 
all of the maps. This leads to constant time operations for lookup. 

### Runtime Analysis
 
