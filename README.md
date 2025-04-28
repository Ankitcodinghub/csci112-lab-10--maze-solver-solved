# csci112-lab-10--maze-solver-solved
**TO GET THIS SOLUTION VISIT:** [CSCI112 Lab 10- Maze Solver Solved](https://www.ankitcodinghub.com/product/csci112-maze-solver-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;116933&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CSCI112 Lab 10- Maze Solver Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
&nbsp;

File names: Names of files, functions, and variables, when specified, must be EXACTLY as specified. This includes simple mistakes such as capitalization.

Documentation: Each file should begin with a docstring that includes your name, the class number and name, the lab number, and a short description of the lab, as well as documentation pertinent to that particular file.

Solving a maze: Now that you know how to generate a maze, solving a maze with depth-first search is easy!

1

In your maze generation program, you found the walls of the maze by repeatedly joining two adjacent cells, putting a “door” between them and erasing the wall. You saved the walls so you could draw them.

Now we want to save all the doors. This will be a list of all pairs of cells that are connected to each other by a door. These pairs form the edges of a graph. Transform this list of pairs into an adjacency list representation of the graph, which can be a dictionary with cells as keys and lists of other cells that are connected to them.

If there is a door between cell a and cell b, be sure to add an edge from a to b and one from b to a!

Depth first search: You can now use a simple stack to search for a solution to the maze. When each node is placed on the “gray” stack, you can record its predecessor in another dictionary. The start node has predecessor None.

When the end node has a predecessor, you can stop the search!

Do not use recursion. Use a stack for depth-first search so that depth-first, breadth-first, and next week’s “greedy” searches all look the same, except for the order of the gray nodes in the data structure.

Random seed: If you want to draw the same maze every time, set the random seed to the same value before shuffling the edges: random.seed(1234), for example.

Drawing the solution: This predecessor list will enable you to draw the solution by starting at the end point, and drawing a line from predecessor to predecessor, until there are no more predecessors.

Feel free to use my drawing code. I’ve modified the drawMaze routine to facilitate drawing the solution path. (It also helps with some “off by one” problems some students had with my original drawing routine.)

After both of these routines have been called, call the plt.show() routine to show the drawing.

def drawMaze(walls, mazeSize): nrows, ncols = mazeSize fig, ax = plt.subplots() ax.axis(“off”) # draw outer box lo = -0.5 hix = ncols-0.5 hiy = nrows-0.5 plt.plot((lo, lo, hix), (hiy-1, lo, lo), color=’black’) plt.plot((lo, hix, hix), (hiy, hiy, lo+1), color=’black’)

# draw walls for wall in walls: a,b = wall y1,x1 = a y2,x2 = b if x1 == x2:

y = (y1+y2)*0.5 plt.plot((x1-0.5,x1+0.5), (y,y), color=’black’)

else:

x = (x1+x2)*0.5

plt.plot((x,x),(y1-0.5,y1+0.5), color=’black’)

def drawPath(predecessors, mazeSize):

nrows, ncols = mazeSize pos = (0, ncols-1) while predecessors[pos] is not None:

y1,x1 = pos

y2,x2 = predecessors[pos]

plt.plot((x1,x2), (y1,y2), color=’red’) pos = predecessors[pos]

plt.plot((ncols),(0), color=’red’, marker=’&gt;’) plt.plot((-1), (nrows-1) ,color=’red’, marker=’&gt;’)

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16

17

18

19

20

21

22

23

24

25

26

27

28

29

30

31

32

2
