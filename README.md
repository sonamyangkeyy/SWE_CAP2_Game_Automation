# SWE_CAP2_Game_Automation
# Programming the Farming Drone (Report)

## Introduction
Farming Drone is a simulation game in which using drone the player gets to manage and plant the farm crops. There are different activities related to agriculture in the game and this means that one is able to make farming activities automatic with the aim of getting the most out of the crops to be produced.
In this case, the goal is to plant crops, manage resources such as time and money well, and harvest good yields. Items can be sold and bought and the use of tools is incorporated to improve farming in order to gain higher yields and to unlock new features.

## Table of Contents
# Code-Snippets and Explanation

## Step 1: Farming on 1 tile

# Pythone, Code:
harvest()
do_a_flip()

# Explanation:
This code use for collecting grass.
Collecting grass will give  hay. Hay can be used to unlock loops in the unlock menu.
while unlock loops. It can also increase the speed of the drone & yield of the grass. By collecting more Grass. It will give more hay, so we can unlock the planting and expands the farm land, unlocks movement.
I have unlocked the while loop and the values True and False. 
 1/    while False:
            do_a_flip()

or

 2/    while True:
            do_a_flip()

The first will never do a flip and the second will do flips forever (an infinite loop). 
I have unlocked the speed of the drone he drone now harvests faster than the grass can grow resulting in no harvest at all. To deal with this <if> branches and the <can_harvest> function are now unlocked.
And again i have unlocked the plant. All other plants have to be planted with the plant() function. The only plant i can plant right now is a bush. By collecting bush will give wood and wood can be used to unlock the operators, carrots, etc..

# Video Demo:
![](Harvest.mp4)


## Step 2: Farming on 1x3 tile


# Pythone, Code:
while True:
    if get_entity_type() == Entities.Bush:
        do_a_flip()
        harvest()
        plant(Entities.Bush)
        move(North)


# Explanation:
The code above contains the use of while loops that are used to look for bushes and when found the code carries out some actions such as flipping, harvesting, planting and moving north.
# Video Demo:
![](operator.mp4)

# Notes:
- Using the code above I was able to get enough Bush to unlock the variable , function ,etc...


# to plant Carrots.

# pythone, Code:
till()
trade(Items.Carrot_Seed)
plant(Entities.Carrots)
# Explanation:
carrots can only grow on tilled soil. To till the soil, we simply code till(). As carrots need seeds to grow, so to call the carrots seeds we have to pass an item type to trade() like trade(Items.Carrot_Seed). & then after finishing all these we can plant carrots.

# to plant Trees
Definitely trees are a better source of getting wood than bushes. They give 5 wood each. Like bushes they can be planted on grass or soil.

Plants like trees need some space from one another if you plant them close together their growth will be slower. For every tree which is on a tile north, east, west or south of it the growing time is doubled. This means that if you planted trees one on each tile then the trees will take 2×2×2×2 = 16 times as long to grow.

## Step 2: Farming on 3x3 tile

# python,code:
while True:
	for i in range(get_world_size()-2):
		harvest()
		trade(Items.Carrot_Seed)
		plant(Entities.Carrots)
		move(East)
		harvest()
		use_item(Items.Water_Tank)
		plant(Entities.Tree)
        move(East)
    move(South)
	for i in range(get_world_size()-2):
		harvest()
		use_item(Items.Water_Tank)
		plant(Entities.Tree)
        move(East)
        harvest()
		plant(Entities.Bush)
		move(East)
    move(South)
    for i in range(get_world_size()-2):
		harvest()
		plant(Entities.Grass)
		move(East)
    move(South)   
	for i in range(get_world_size()-2):
		harvest()
		plant(Entities.Grass)
		move(East)
        harvest()
		plant(Entities.Grass)
		move(East)
    move(South) 

# Explanation:
-Infinite Loop:
The process continues in cycles and cycles, from one stage to the other.

-First Loop:
Harvest crops.
Exchange carrots seeds and plant carrots.
Go East, pick crops one more time, and water some plants.
Plant a tree and move east again…
If finished, shift downwards toward the below row sitting in the South direction.

-Second Loop:
Harvest crops.
Irrigate the plants, and copy trees.
Go East, reap, and then sow plants.
Once this loop is over go South.

-Third Loop:
Harvest and plant grass.
Change position Eastward after every planting.
Move South when done.

-Fourth Loop:
Sell grain, sow the lawn, and go east.
Harvest again, plant with grass again and go east.
Move South after finishing.

# Video Demo:
![](without.mp4)


# Notes:
Using the code above I was able to get enough hay, woods, carrots to unlock the pumpkins, variables, function, etc...


--The code below is the same as above,there’s only a slight change in it.
It’s to harvest the tree between the carrot and the grass.

# planting the trees between the others plants like carrots, grass

# pythone, Code:
while True:
	for i in range(get_world_size()-2):
		harvest()
		trade(Items.Carrot_Seed)
		plant(Entities.Carrots)
        move(East)
        harvest()
		use_item(Items.Water_Tank)
		plant(Entities.Tree)
        move(East)
		harvest()
		trade(Items.Carrot_Seed)
		plant(Entities.Carrots)
        move(East)
	move(South)
    for i in range(get_world_size()-2):
		harvest()
		use_item(Items.Water_Tank)
		plant(Entities.Tree)
        move(East)
		harvest()
		trade(Items.Carrot_Seed)
		plant(Entities.Carrots)
        move(East)
		harvest()
		use_item(Items.Water_Tank)
		plant(Entities.Tree)
        move(East)
	move(South)
	for i in range(get_world_size()-2):
		harvest()
		plant(Entities.Grass)
        move(East)
        harvest()
		use_item(Items.Water_Tank)
		plant(Entities.Tree)
        move(East)
		harvest()
		plant(Entities.Grass)
        move(East)
    move(South)


## Explanation
Infinite Loop:The code runs in endless cycle to give repeated operations in farming.

-First Loop:
Iterates through each plot in the row:
    Harvest crops.
    Trade for carrot seeds.
    Plant carrots.
    Move East and harvest again.
    Water the crops using a water tank.
    Plant a tree.
    Move east and do the same thing.
    After completing the row, go along South.
-Second Loop:
    Similar structure, but:
    Use water to water the plants before planting trees.
    Trade for carrot seeds, and put in more carrot plants.
    Finish by moving South.
-Third Loop:
    Focuses on grass and trees:
    Harvest, then plant grass.
    East will introduce harvest; next is watering and planting of trees.
    Finally wrap up the whole activity by planting grass again.

# Video Demo:
![](trees.mp4)

## plant sunflower
# pythone, Code:
for i in range(get_world_size()):
      
      trade(Items.Sunflower_Seed)
      plant(Entities.Sunflower)
      move(East)
	move(South)
	for i in range(get_world_size()): 
      
      trade(Items.Sunflower_Seed)
      plant(Entities.Sunflower)
      move(East)
	move(South)
    for i in range(get_world_size()):
    
      trade(Items.Sunflower_Seed)
      plant(Entities.Sunflower)
      move(East)
	move(South)
    for i in range(get_world_size()):
        num_petals = measure()
       
    do_a_flip()
    do_a_flip()
    do_a_flip()
    do_a_flip()
    do_a_flip()
    do_a_flip()
    do_a_flip()
    do_a_flip()

# Explanation:
-Outer Loop:
Proceeds for the world size and goes through it.
-Planting Sunflowers:
In each row, the character:
Trades for sunflower seeds.
Plants sunflowers.
Moves East to the next plot.
It will then turn right and move South to the next row and it will perform this three times.
-Measuring Petals:
After planting it counts the no of petals for each plot in the world.
The character does a flip animation eight times which is added after the completion of the tasks.

# Video Demo:
![](sunflower.mp4)

## Step 2: Farming on 4x4 tile
## to find treasure:

# pythone, Code:
def coord():
	return [get_pos_x(),get_pos_y()]
directions = [North,West,South,East]
x = 0
for i in range(300):
	visited = []
	while get_entity_type() != Entities.Treasure:          
		while not move(directions[x]):
			x += 1
			if x == 4:
				x = 0
		x -= 1
		if x == -1:
			x = 3
while get_entity_type() == Entities.Treasure:
	while not (Items.Fertilizer,5):
		harvest()
		plan_pumpkines(10000)
	use_item(Items.Fertilizer)

# Explanation:
-Function:
coord() gives information of the current position of the character in the x and y axis.

-Directions:
The list directions defines movement options: North, West, South, and East.

-Main Loop:
Drone spends 300 times running around to look for the treasure .

-First While Loop: They have no limit and lasts until the character finds treasure.
Tries to step in the current direction.
If movement fails, it then goes to the next direction.
Checks whether the new direction index is out of an appropriate range then corrects it accordingly.

-Treasure Handling:
Second While Loop: Stays active as long as the character is on a treasure.
If the character has less than 5 units of fertilizer then it harvests resources and plants pumpkins.
Last of all, it uses fertilizer when available Last of all, it uses fertilizer when available.

# Video Demo:
![](Treasure.mp4)

## Challenges
Resource Management: Seed and fertilizer distribution/ Handing out seeds and fertilizers equitably to make the competition fair.
It is difficult to Developing smart movements of the drone to ensure that it does not collide with any object.

## Learnings
Resource Management:
Useful in establishing the various means of implementing resources that are dynamic: I made the drone access the seeds as well as the fertilizers depending on its current necessity.

State Management: Controlled the position and inventory of the drone to make it as smooth as possible during the game.

## References
1. [Resource 1 ](https://youtu.be/Pzu2bHR1fP8?si=2dACNpdIfQ10gLMS)