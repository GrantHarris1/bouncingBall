// Creating new objects

Change Ball() to Shape() constructor
* make Shape difine x,y,velX,velY same as Ball() did.
* Define new property called 'exists', to track wether ball exists in program. should be boolean (true/false).
* Ball() to inherite properties from the Shape() contructor.
    * should also difine color & size like 'Ball' did.
* Set Balls Constructors prototype and constructor appropriately.
* Ball prototytpe's collisionDetect() should be small update. if kept as is EvilCircle would start eating the bouncing balls by setting exists property to 'false'. Would reduce the number of balls involved in collision detection.A ball needs to be considered for collision detection only if the exists property is 'true'. Replace the existing collisionDetect() code with the following code:

Ball.protoype.collisionDetect = function() {
    for (let j = 0; j < balls.length; j++) {
        if (!(this === balls[j]) && balls[j].exists) {
            const dx = this.x - balls[j].x;
            const dy = this.y - balls[j].y;
            const distance = Math.sqrt(dx * dx + dy * dy);
            if (distance < this.size + balls[j].size) {
                balls[j].color = this.color = 'rgb(' + random (0,255)
            }
        }
    }
}

only addition is the check f ball exists using balls[j].exists in the 'If' coditional.

// defining Evil Circle

Evil Circle should inherit x,y,velX, velY, exists from Shape(), but velX, velY should always = 20.

Do Shape.call (this, x,y,20,20, exists)
*should difine own properties
    *color-'white'
    *size - 10