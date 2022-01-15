[[My CS Cheat Sheet]]

# SIMPLECPP

[Simplecpp Webpage](https://www.cse.iitb.ac.in/~ranade/simplecpp/)

```
#include<simplecpp> // Include this header file
main_program {
    // this is a comment
    // this is our opening function
    
    initCanvas("title", 800, 800); // this is to create a canvas (without turtle) of size 800x800
    // OR turtleSim("title", 800, 800); // this is to create a canvas (with turtle) of size 800x800
    Turtle t1,t2,t3,t4; // create 4 turtles named t1, t2, t3, t4
    
    /* BTW, this is a multiline comment*/

}
```

## registered commands
##### turtle commands =>
```
forward(x); // move the turtle forward x pixels, where x is a real number
t1.forward(x); // move the turtle named t1 forward x pixels

left(x); // turn the turtle left by x degress, where x is a real number
t1.left(x); // turn the turtle named t1 left by x degress
right(x); // turn the turtle right by x degress, where x is a real number
t1.right(x); // turn the turtle named t1 right by x degress

penUp(); // lift the turtle
t1.penUp(); // lift the turtle named t1
penDown(); // lower the turtle
t1.penDown(); // lower the turtle named t1
```
- Pens of non-turtle shapes are UP by default
---

##### shape commands
```
/* 
BASIC SYNTAX 
shape-type name(arguments); // shape-type = Circle, Rectnagle, Line, Text

name.forward(100); // move the object named 'name' forward by 100 pixels

Circle c1(100,100,10), c2(100,100,20); // first 2 numbers are (x,y) coordinates of centre, and 3rd is the radius
Rectangle r1(100,100,30,40); // first 2 numbers are (x,y) coordinates of centre, while 3rd and 4th are width and height
Line l1(20,30,40,50); // create a line from (20,30) to (40,50)
Text t1(100,100,"C++"); // first 2 numbers are (x,y) coordinates of the centre, while 3rd is the string to be printed

// commands textWidth(t) and textHeight(t) evaluate to the width and height of the text t in pixels
```

```
// let 's' be a shape created earlier

s.moveTo(x,y); // move object s to (x,y)
s.move(dx,dy); // move object s by (dx,dy)
s.scale(factor); // scale object s by factor
s.rotate(angle); // rotate object s by angle(radians)
// rotate and scale cannot happen with text

s.penDown(); // use centre of shape as a drawing pen/turtle
s.penUp(); // lift the shape up

s.setColor("red"); // set color of object s to "red"
// OR s.setColor(255,0,0); // using RGB code for the color

// if s is a rectangle/circle
s.setFill(true); // set fill color of object s same as border color

s.getX(); // returns the x-coordinate of the object s
s.getY(); // returns the y-coordinate of the object s
s.getOrientation(); // returns the angle through which the object s has been rotated
s.getScale(); // returns the scale-factor of the object s
s.imprint(); // permanently imprint a duplicate of object s

```
---

##### regular commands
```
repeat(n) {//code}; // repeat some code n times

cout<<x<<endl; // print the value of x, then break line, in terminal
cin>>x>>y; // input the value of x, put a space, then input the value of y, in terminal

wait(5); // wait for 5 seconds

getClick(); // pause the program till the user clicks, and return 65536x + y

```

---

##### math operations

```
sqrt(x); // square root of value of x
pow(x,y); // x raise to power y
exp(x); // e raise to power x
log(x); // logarithm of x to the base e
log10(x); // logarithm of x to the base 10

sin(x); // find sine of x, x being in radians
cos(x); // find sine of x, x being in radians
tan(x); // find sine of x, x being in radians

sine(x); // find sine of x, x being in degrees
cosine(x); // find sine of x, x being in radians
tangent(x); // find sine of x, x being in radians
```

##### conditional execution
```
if (x) {//code if x is true, then go to HERE}
else if(y) {//code if x is false, and y is true, then go to HERE}
else if(z) {//code if x and y both are false, and z is true, then go to HERE}
else {//code if x,y,z are all false, then go to HERE}

// HERE
// basically, it's a ladder-work
```

```
while(//condition) {
    //code to run in loops as long as condition is true
}
```

```
for(initialization; condition; update) { // execute initialization once
    // execute this code if condition is true, then execute update
    // recheck condition, and repeat
    // NOTE : new variables defined in initialization have their scope restricted to the loop
    //        Also, clashing variables will lead to the localized loop variables being used
    // break(); and continue(); functions can be used here
}
```
---
## Methods
[[how_to_draw_a_circle.cpp]]
[[replace_for_loop_with_repeat.cpp]]
[[replace_repeat_with_while_loop.cpp]]

## Examples
[[maclaurin_series_for_e.cpp]]
[[n-point star V3.cpp]]
[[n-point star V2.cpp]]
[[plate_border_design.cpp]]
[[hilbert v1.cpp]]
[[projectile_motion.cpp]]
[[tax_calc_program.cpp]]

### pending stuff
![[Pasted image 20211219202609.png]]
![[Pasted image 20211219202723.png]]
![[Pasted image 20211219202749.png]]

![[Pasted image 20211219203329.png]]
![[Pasted image 20211219203346.png]]

![[Pasted image 20211219203629.png]]
![[Pasted image 20211219204042.png]]
![[Pasted image 20211219210650.png]]

---

![[Pasted image 20211219221138.png]]
![[Pasted image 20211219221200.png]]
![[Pasted image 20211219222656.png]]
![[Pasted image 20211219222709.png]]

### pending examples
![[Pasted image 20211215212723.png]]
![[Pasted image 20211215212757.png]]
![[Pasted image 20211215212912.png]]
![[Pasted image 20211215212926.png]]
![[Pasted image 20211215212937.png]]
![[Pasted image 20211215212947.png]]
![[Pasted image 20211215213000.png]]