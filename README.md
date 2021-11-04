# This is my second marked lab exercise!!!

This lab exercise consists of 10% of my final grade.

## Lab 2

###`We would like to create an interactive game where a character is controlled by the player to achieve an objective. It promotes object programming with JavaScript and the use of the DOM API. The characters are bees and a bear. The bees fly randomly in all directions to attack the bear. The bear is controlled by the user and can move up, down, left, and right while staying in the game board to avoid being bitten by bees. The objective of the player is to minimize the number of stings. The winner is the player who manages to have less stings. The user must be able to adjust, on the run, the speed of the bees and the frequency of the game update loop. They can also restart the game and set any the number of bees to play with. Bees appear at random positions in the board and move continuously and randomly in the four directions. The application should detect any sting (overlap between a bee and the bear images). The number of stings is displayed continuously. The duration between two stings is also calculated. The longest period without stings is kept as the best score. The largest duration is displayed and refreshed every time it changes. The user can add bees at any time without restarting the game.`
###HTML & CSS

- Create the web page of the game.
- Using HTML and CSS, start creating a web page that looks like the above, with preferably three div
  element:
- div title
- div scores
- div board
- Add the bear image to the board div
  ###Bear motion
- We first create JavaScript code to control the movement of the bear.
  Create the file game.js and link it to the HTML file by adding the following to the head
  section.
- To control the bear position in the game board, we create a class that holds the HTML
  attributes of the bear image. We also add two functions (or methods):
- move() to move the bear by dx and dy steps in the horizontal and vertical directions.
- display() to display the bear at the new position in the game.js file.
- The attribute dBear is the step (in pixels) made by bear when the user clicks an arrow on the
  keyboard. notice the use of the DOM API I the move function and in the display function.
- Testing the page does not bring any change yet. We need to instantiate the Bear object. For
  this purpose, we need to create a global variable when the page first loads. This variable
  declaration is done in the head section of the HTML file.
- Testing the page does not bring any change yet. We need to instantiate the Bear object. For
  this purpose, we need to create a global variable when the page first loads. This variable
  declaration is done in the head section of the HTML file.
- To invoke the start() function, we add onload event to the body tag in the HTML page.
- This will invoke the start() function when the page finishes to load.
  Now, to be able to control the movement of the bear, we create an event handler for keyboard
  events (Up, Down, Left, Right) – Notice the call to the function move() of the bear object.
- The bear does not move yet! We need to associate the event handler to the bear image (the
  IMG tag). We do this in the start() function using the DOM API function addEventListner().
- We
  need to fit the bear to the board limits. For this, we add the following function in the bear
  class (notice again the use of the DOM API).
- We call this function from the move() method.
- Create an input field for the user to enter the speed (dBear) of the bear. Make the
  necessary changes to read the value entered by the user to modify dBear.
  ###Adding bees to the board.
- The Bee class allows creating and controlling instances of bee objects (IMG tags in the
  HTML file). We first add the Bee class to game.js.
- The class has attributes of the bee IMG element from the HTML file and methods to move
  and display the bee (like the bear). However, the IMG element must be created and added to
  the web page, precisely in the board div. This is done by calling the createBeImg() function,
  which create the IMG element, add it to the DOM tree, and sets its initial position randomly.
- Write the function getRandomInt(max) that generates and returns a random
  integer between 0 and max.
- To add the number of bees specified by the user in the input field (nbBees), we create a
  global variable (var bees;) in the <script> tag I the header section of the HTML.
- The actual creation of the bees is done in the method makeBees().
- For this to work, we need to call makeBees() from the start() function.
  ###Animate the bees.
- We first write a function moveBees() that displaces each bee to a random location (dx, dy).
  Notice the use of the speedBees input value to control the speed of the motion.
- To get the bees to move continuously, we will use a timer.
- The updateTimer variable must be declared global in the <script> tag in the HTML file. The
  initial call to updateBees() is done in the start() function.
- Change the code in updateBees() to use the input field periodTimer instead of the fixed
  period (10).
  ###Count the stings.
- We consider that whenever a bee image intersects with the bear image a sting has happened.
  We would like to count the stings and display the number in the “hits” span element of the
  HTML file.
  The isHit() method checks if two elements overlap.
- We consider that whenever a bee image intersects with the bear image a sting has happened.
  We would like to count the stings and display the number in the “hits” span element of the
  HTML file.
- The isHit() method checks if two elements overlap.
- It uses the function overlap() that determines the intersection between the two elements.
- To count the stings, we call the isHit() method when we move each bee in moveBees().
- Change the code to stop the game and display “Game over!”, when the number of stings
  reaches 1000.
  ###Calculating the longest escape duration.
- In addition to the number of stings, we would like to measure and display the longest
  duration the player manages to hold between two consecutive stings. For this, we modify the
  isHit() method.
  ###Additional features.
- Create a “restart” button in the HTML file to re-initialise the game.
- Create a “restart” button in the HTML file to re-initialise the game.
