Download Link: https://assignmentchef.com/product/solved-cs2030s-problem-set-1-basics-of-object-oriented-programming
<br>
Problem Set #1 <strong>Basics of Object-Oriented Programming</strong>

<ol>

 <li>Consider the following two classes:</li>

</ol>

class P { private int x;

void changeSelf() { x = 1;

}

void changeAnother(P p) {

p.x = 1;

}

}

class Q { void changeAnother(P p) {

p.x = 1;

}

}

<ul>

 <li>Which line(s) above violate the private access modifier of x?</li>

 <li>What does this say about the concept of an “abstraction barrier”?</li>

</ul>

<ol start="2">

 <li>Consider the following definition of a Vector2D class:</li>

</ol>

class Vector2D { private double x; private double y;

Vector2D(double x, double y) { this.x = x; this.y = y;

}

void add(Vector2D v) { this.x = this.x + v.x; this.y = this.y + v.y;

// line A

}

}

<ul>

 <li>Suppose that the following program fragment is executed in JShell, show the content of the stack and the heap when the execution reaches the line labelled A</li>

</ul>

Vector2D v1 = new Vector2D(1, 1); Vector2D v2 = new Vector2D(2, 2); v1.add(v2);

Label your variables and the values they hold clearly. You can use arrows to indicate object references.

<ul>

 <li>Suppose that the representation of x and y have been changed to a double array:</li>

</ul>

class Vector2D { private double[] coord2D;

…

}

<ol>

 <li>What changes do you need for the other parts of class Vector2D?</li>

 <li>Would the program fragment in 2a above be valid?</li>

</ol>

Show the content of the stack and the heap when the execution reaches the line labelled A again.

<ol start="3">

 <li>Below is our familiar Point classes augmented with a toString method.</li>

</ol>

class Point { private final double x; private final double y;

Point(double x, double y) { this.x = x; this.y = y;

}

double distanceTo(Point otherpoint) { double dispX = this.x – otherpoint.x; double dispY = this.y – otherpoint.y; return Math.sqrt(dispX * dispX + dispY * dispY);

}

@Override

public String toString() { return “(” + this.x + “, ” + this.y + “)”;

}

}

The toString method provides a way to output an object in a more meaningful way, rather than just a reference value. To illustrate using JShell,

jshell&gt; /open Point.java

jshell&gt; Point p = new Point(0, 0) p ==&gt; (0.0, 0.0)

You are also given the Circle class.

class Circle { private final Point centre; private final double radius;

Circle(Point centre, double radius) { this.centre = centre; this.radius = radius;

}

boolean contains(Point point) { return centre.distanceTo(point) &lt;= radius;

}

@Override

public String toString() { return “Circle centred at ” + this.centre


” with radius ” + this.radius; }

}

We can define an array of five points as follows:

jshell&gt; Point[] points = new Point[]{new Point(0,0), new Point(0,-1),

…&gt; new Point(1,0), new Point(0,1), new Point(-1,0)}; points ==&gt; Point[5] { (0.0, 0.0), (0.0, -1.0), (1.0, 0.0), (0.0, 1.0), (-1.0, 0.0) }

<ul>

 <li>Within JShell, define a method countCoverage that takes in a Circle object, and an array of Point This method will return the number of points contained within the circle.</li>

 <li>Write single line tests in JShell to test the correctness of the method. For example,a circle centred at the origin with radius 1<em><sub>.</sub></em>0 contains all five points; a circle centred at (0<em><sub>.</sub></em>0<em><sub>,</sub></em>−1<em><sub>.</sub></em>0) with radius 1<em><sub>.</sub></em>0 contains two points.</li>

</ul>