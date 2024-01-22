let characterSizeSlider;
let backgroundColorPicker;
let posX = 40;
let posY = 40;
let speed = 5;
let movingUp = false;
let movingDown = false;
let movingRight = false;
let movingLeft = false;


function setup() {
  createCanvas(400, 400);
  strokeWeight(4);

  // Slider for character size
  characterSizeSlider = createSlider(0.1, 2, 0.25, 0.1);//(Smallest value, largest value, default value, increment)
  characterSizeSlider.position(30, 470);//represents where the slider will be on the canvas

  // Color picker for background color
  backgroundColorPicker = createColorPicker('#7DFF7D');//Represents the color function of backgroundColorPicker and the default color of the background
  backgroundColorPicker.position(40, 430);//Represents where the colorPicker will be in the canvas

}

function drawCharacter(x, y, size) {
  // Your character drawing code goes here, using x, y, and size
  // Example: ellipse(x, y, 50 * size, 50 * size);
  // ...

  // legs
  fill(255, 192, 203);
  rect(x - 80 * size, y + 50 * size, 25 * size, 125 * size);
  rect(x + 50 * size, y + 50 * size, 25 * size, 125 * size);

  fill(0, 0, 0);
  rect(x - 80 * size, y + 150 * size, 25 * size, 25 * size);
  rect(x + 50 * size, y + 150 * size, 25 * size, 25 * size);

  // body
  fill(255, 192, 203);
  ellipse(x, y, 260 * size, 200 * size);

  // ears
  ellipse(x - 35 * size, y - 54 * size, 25 * size, 45 * size);
  ellipse(x + 35 * size, y - 54 * size, 25 * size, 45 * size);

  // face
  fill(255, 192, 203);
  ellipse(x, y, 120 * size, 135 * size);

  // eyes
  fill(255, 255, 255);
  circle(x - 25 * size, y - 20 * size, 25 * size);
  circle(x + 20 * size, y - 20 * size, 25 * size);

  fill(0, 0, 0);
  circle(x - 25 * size, y - 25 * size, 10 * size);
  circle(x + 20 * size, y - 25 * size, 10 * size);

  // nose
  fill(255, 192, 203);
  ellipse(x, y + 22 * size, 50 * size, 25 * size);
  fill(0, 0, 0);
  circle(x - 10 * size, y + 22 * size, 10 * size);
  circle(x + 10 * size, y + 22 * size, 10 * size);

  // mouth
  noFill();
  arc(x, y + 40 * size, 35 * size, 35 * size, 0, 3, OPEN);
  
}

function drawMaze() {
  // Maze drawing code
  // Basic maze structure
  stroke(0); // Black color for the maze
  noFill();
  
    // structure of code line(x1, y1, x2, y2);
    // walls
    line(100, 0, 100, 300);
    line(200, 100, 200, 400);
    line(300, 0, 300, 300);
  
}
function keyPressed() {
  //This section shows how each arrow being pressed will move the pig character
  if (keyCode === UP_ARROW) {
    movingUp = true;
  } else if (keyCode === DOWN_ARROW) {
    movingDown = true;
  } else if (keyCode === RIGHT_ARROW) {
    movingRight = true;
  } else if (keyCode === LEFT_ARROW) {
    movingLeft = true;
  }
}
  //this will ensure that the pig character will stop moving when the direction previously requested to move at is let go
  function keyReleased() {
  if (keyCode === UP_ARROW) {
    movingUp = false;
  } else if (keyCode === DOWN_ARROW) {
    movingDown = false;
  } else if (keyCode === RIGHT_ARROW) {
    movingRight = false;
  } else if (keyCode === LEFT_ARROW) {
    movingLeft = false;
  }
}
  // function for backgroundColorPicker and characterSizeSlider was previously announced but it must be drawn in order to be in the code
  // backgroundColorPicker would maintain its default color which was previously mentioned and not change as it was in function setup, being in function draw allows it to constantly change
  function draw() {
  background(backgroundColorPicker.color());

  let characterSize = characterSizeSlider.value();
  drawMaze();

  // Move the character continuously while the key is pressed
  if (movingUp) {
   posY -= speed;
  }
  if (movingDown) {
   posY += speed;
  }
  if (movingRight) {
   posX += speed;
  }
  if (movingLeft) {
   posX -= speed;
  }

  drawCharacter(posX, posY, characterSize);
}
