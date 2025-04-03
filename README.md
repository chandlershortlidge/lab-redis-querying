![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Lab | Redis: Querying the Movies Dataset

This lab is designed to help you practice creating custom classes, defining operators, and writing functions in R. Follow the instructions and complete the tasks below.

## Task 1: Create a Custom S3 Class

1. Define a custom S3 class called "Circle" that represents a circle. The class should store the radius of the circle.
2. Write a constructor function Circle() that takes the radius as input and assigns the class "Circle" to the object.
3. Write a print.Circle() method to display the radius and area of the circle when the object is printed. Use the formula for the area of a circle: area = π * radius^2.

**Example:**
```r
my_circle <- Circle(5)
print(my_circle)
```
**Output:** <br>
Type: "Circle object" <br>
Radius: 5<br>
Area: 78.53982<br>

## Task 2: Define a Custom Operator

1. Define a custom operator %>% that calculates the distance between the centers of two circles and checks if they intersect. The operator should return TRUE if the circles intersect and FALSE otherwise.
The formula for the distance between two circles is: distance = sqrt((x2 - x1)^2 + (y2 - y1)^2).
	- Assume that the circles are centered at (x1, y1) and (x2, y2), respectively.
	- Two circles intersect if the distance between their centers is less than or equal to the sum of their radii.
2. Modify the Circle class to include x and y coordinates for the center of the circle.

	**Example:**
	```r
	circle1 <- Circle(radius = 3, x = 0, y = 0)
	circle2 <- Circle(radius = 4, x = 5, y = 0)
	circle1 %> circle2
	```
	**Output:** TRUE

## Task 3: Write a Function for the Class

1. Write a function circumference() that calculates the circumference of a Circle object. The formula for the circumference is: circumference = 2 * π * radius.
2. Add this function as a method for the Circle class so that it can be called directly on objects of the class.

	**Example:**
	```r
	my_circle <- Circle(radius = 5)
	circumference(my_circle)
	```
	**Output:** 31.41593

## Task 4: Create a Custom S4 Class
	
1. Define a custom S4 class called "Rectangle" that represents a rectangle. The class should store the length and width of the rectangle.
2. Write a constructor function Rectangle() that takes the length and width as input and creates an object of the "Rectangle" class.
3. Write a show() method for the Rectangle class to display the length, width, and area of the rectangle when the object is printed.

	**Example:**
	```r
	my_rectangle <- Rectangle(length = 4, width = 6)
	show(my_rectangle)
	```
	**Output:** <br>
	Type: "Rectangle object" <br>
	Length: 4 <br>
	Width: 6 <br>
	Area: 24<br>

## Task 5: Define a Custom Operator for the S4 Class

1. Define a custom operator %==% that compares two Rectangle objects and checks if they have the same area.
2. The operator should return TRUE if the areas are equal and FALSE otherwise.

	**Example:**
	```r
	rectangle1 <- Rectangle(length = 4, width = 6)
	rectangle2 <- Rectangle(length = 3, width = 8)
	rectangle1 %==% rectangle2
	```
	**Output:** TRUE

### Resources

- [R Documentation on S3 Classes](https://adv-r.hadley.nz/s3.html)
- [R Documentation on S4 Classes](https://adv-r.hadley.nz/s4.html)
- [R Operators](https://stat.ethz.ch/R-manual/R-devel/library/base/html/Arithmetic.html)

## Deliverables

- Submitted notebook (or file) with your responses to each of the exercises.

## Submission

- Upon completion, add your deliverables to git. 
- Then commit git and push your branch to the remote.
- Make a pull request and paste the PR link in the submission field in the Student Portal.

<br>

**Good luck!**
