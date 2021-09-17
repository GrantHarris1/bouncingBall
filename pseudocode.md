# Creating new objects

### Changing ball construstor to Shape: newShape

function Shape(x, y, velx, vely, exists){
this.x = x;
this.y = y;
this.velX = velX;
this.velY = velY;
this.exists = exists;
};
____
### NEW Ball constructor. newBall:

function Ball(x, y , velX, velY, exists); /*inherits from shape */
Shape.call(x, y, velX, velY, exists, color, size){
    this.color = color; // brought from old BALL
    this.size = size
}
____
#### Balls prototype and construtor

Ball.prototype = Object.create(Shape.prototype);
Ball.prototype.constructor = Ball;
____
### Change Balls collisionDetect() 

Use new sample code to replaces ball collision detect.
* if statement is where Balls exists in the conditional.
____
#### Draw and Update constructors for Bll stay the same.
___
# Evil Circle
### Defining evilCircle
* Inherits from Shape()
    * velx, velY = 20
    * properties color: white, size:10
* Shape.call (this,x,y,20,20,exists)






## evilCirlce Methods
### Draw()
* Copy Balls draw, then change:
    * Change fillStyle to strokeStyle
    * Change fill to stroke
    * Call linewidth to 3
___

### checkBounds()
* Copy: Ball.protoype.update, then change:
    * Get rid of the last 2 lines,
    * inside *if* if test returns true dont update velX/velY rather change the value of x/y so evilCircle bounces back on screen. add or subtracting the size property.
___

### Set Controls
* Put sample code for onkeydown inside the method definition
    * sets key controls for " d,w,s,a"
___

### evilCollision Detect
* Copy Balls collision detect()
    * Change outer *if* statement to no longer check if current ball in the iteration is the same as the ball that is ding the checking. Instead check to see if ball being checked exists.
    * in the inner *if* statement, dont make objects cange color when collison, instead ste them to not exist any longer.
___
### evilCircle into program
* Changses to loop function
* Create new evilCircle object instance
    * call its set controls
    * only needed once
* Where you loop through every ball call your draw(),update(),and collisionDetection() functions put these inside where the ball 'exists'
* call Balls instance: draw(),checkBounds(), and collosiionDetect() methods on every itereation of loop.
___

### Score Counter

* Add <p> in HTML
    * add text : Ball count
* Add css provided in sample
* in JS create a Var that references the Para.
* keep count of balls.


    
