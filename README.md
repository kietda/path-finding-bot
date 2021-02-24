A* Project

# Intro:
  1. This bot uses A* algorithm to estimate cost of near-by tiles and move to the best-cost tile.
  2. Algorithm for bot moving:
    - Add start node to list
	- Check status of 4 kids adjacent of the current node (floor, not in closed list), add them to open list, move current node to close list.
		+ If the kid is not on the open list, calculate its g,h,f and  add it to the open list.
		+ If the kid is already on the open list, check if the path current node offers costs less than the current path 
			- If it does so, remove the old node, add the new node (this kid) to the open list
			- If not, keep the old node and skip this kid.
	- Get the least cost f(n) node (1st member of list), and repeat the above step.
	- Stop working when
		+ Bot reaches the goal cell
		+ There’s no possible path (open list is empty)

# Contents: Files Included:
  0-README.txt -- This file.
  project1_algo_report.pdf -- Project Algorithm Report
  Jathp.js -- The modified Javathcript.js file; for original use websearch.
  cs-sketch-paint.js -- Has P5 key animation fcns: setup() and draw() + my globals. 
  index-js-p5-jathp-5.html -- Main webpage in HTML + JS + JP.
	Also has has the jp-draw-maze fcn in the html (at bottom)
  p5.js -- The P5 system; unmodified, from its github site.
  assets/
    draw-stuff.js -- Has P5 draw_grid() fcn [simpler that JS drawing].
    styles.css -- Cascading Style Sheet (CSS) micro-example.

# Installation:
  0. This zip includes all P5 and Jathp; browser already does HTML & JS.
  1. Unzip the zip file into a folder.
  2. Change directory into folder's js-p5-jathp-maze/.
  3. Open your Broswer to an empty tab.
  4. Drag index-js-p5-jathp-5.html into the tab & see it start to run.
  5. See the grid maze created.
  6. See the bot run
	- Green: best path from start node to current node
	- Beige: cells bot visited.  
  7. Open the Inspector-Console-Debugger pane with your F12 key.
  8. Select the Console tab to see the console.log text output stream.
  9 Bot will stop when it reaches the goal (cell(35,26))

# Feature:
  - Use Heuristic Function, F(N) = G(N) + H(N), to best first search (A* Algorithm)
  - Show the bot as a read circle. Bot will move orthogonally to a neighboring tile.
	+ Bot always choose the best node (best f(n), min y, min x) as its destination.
  - Highlight the best path (shortest) from start to current node (green)
  - Highlight the cell visited (beige)
  - Show a 2-digit f(n) number in each of the as-yet-unvisited kid cells that has been evaluated (in open list)
  - Once bot reaches the goal tile (cell (35 26)), it will stop.
Bugs:
  - Decrease the value of g_frame_mod (in cs-sketch-paint.js file) lower (e.g., 2) to make the bot run faster. However, it may make the canvas stop working when user refreshes the browser. 
    + User can fix by closing browser, re-opening browser, and refreshing browser several times can make it run.
