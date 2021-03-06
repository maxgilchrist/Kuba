# Kuba
Max Gilchrist, Kevin Li

Gamescrafters Theory Team

## SP 20 Write Up 
Here are two references to the Kuba game and instructions:
[Rules 1](http://www.di.fc.ul.pt/~jpn/gv/kuba.htm)
[Rules 2](https://sites.google.com/site/boardandpieces/list-of-games/kuba)

### Board Count
We broke down the board into three possible cases: (1) all possible positions with at least one white and one black marble, (2) all winning board positions for white with no black marbles, and (3) all winning board positions for black with no white marbles. 

Case 1: <img src="https://github.com/maxgilchrist/Kuba/blob/master/Images/case1.png" height="75">

Case 2: <img src="https://github.com/maxgilchrist/Kuba/blob/master/Images/case2.png" height="75">

Case 3: <img src="https://github.com/maxgilchrist/Kuba/blob/master/Images/case3.png" height="75">

The total sum was 1.24E26.

### Smaller Possibilities
Given that our count was too large, we experimented with three smaller, 5x5 versions of the game.

<img src="https://github.com/maxgilchrist/Kuba/blob/master/Images/225.png" width="250">
<img src="https://github.com/maxgilchrist/Kuba/blob/master/Images/2213.png" width="250">
<img src="https://github.com/maxgilchrist/Kuba/blob/master/Images/885.png" width="250">

We found that the 5x5 board with 2 starting whites/blacks and 5 reds best maintained the overall strategic features of the original game.

The Tier Counts for each are [here](https://github.com/maxgilchrist/Kuba/tree/master/Output)

### Hashing

#### Overview
The end goal is to create a triple tier hash dictonary
the way at the end the API for this structure
should addPosition(position) lookup(position)
The triple tiered dictonary is comprised of 
three layers. 
**First Layer** - Counts red and returns pointer to correct second layer
**Second Layer** - Counts white and returns pointer to correct third layer
**Third Layer** - Counts black and returns pointer to the correct hashmap

As we already have an upperbound on the number of positions in each tier
we have intialized all of the hashmaps with that size and this 
gurantees that our load factor = (n/k) < 1 where n is the number of entries
and k is the number of bucks. 

#### Symmetries
We can use symmetries in order to lower the entries in each table. Once, we have
computed the actual tree once we have a precise value of k such that n = k for 
all of the maps. This leads to constant time operations for lookup. 

### For the future
In future semesters, we hope to finish designing a hash for the tiers of 2,2,5 and be able to solve it.
