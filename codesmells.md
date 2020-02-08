# Markdown

Markdown is a plain-text file format. There are lots of programming tools that use Markdown, and it's useful and
easy to learn. Hash marks (the number sign) indicate headers. Asterisks indicate lists.

# List of code smells

## Code Smell 1: [Main class has a very long start method]

### Code Smell Category: [Long Method]

### List of classes and line numbers involved:

* Class Main
* Line number 110-153.

### Description:

This method contains a very large number of lines of codes(nearly 90 lines). And a lot of codes are simply repated logic with different values applied.

### Solution:

For the line 50-75 in the original Main.java, they are simply doing some data populating work, thus I need to take them out and create a separate method containing these lines.

### Explanation

Firstly, I group these lines of code into a standalone method named populateFarmObjectsList().
Secondly, I only need to make a simple call to populateFarmObjectsList() now in the start() method.
Finally, there are several repeated code in the populateFarmObjectsList() as well as some codes that are being overriden by later codes, thus I removed those unnecessary code as well.
Also, since the codes all do the same thing with different objects, another utility method is extracted:populateFarmObject(FarmObject fo,int c, int r). Then well only need to pass the object and coordinate information to this method.
============================================================

## Code Smell 2: [A very long method contains too much logic]

### Code Smell Category: [Long method]

### List of classes and line numbers involved:

* Class main
* Line number 66-106

### Description:

The start() method in Main class should only consist of logics that does game prepartion, but it also contains a big chunk of closure code that does game loop event handling.

### Solution:

Move all the game loop handling logic into a separate method called gameLoop(GraphicsContext gc), and it will does all the event watching throughout the course of the game.
Also, a parameter should be supplied in the start() method, which is the GraphicContext for rendering.

### Explanation

Thus the game loop logic detail is no longer bothered with start() method, the start() method only needs to register the handler when program initiates.

============================================================

## Code Smell 3: [More constants]

### Code Smell Category: [Primitive Obsession]

### List of classes and line numbers involved:

* Human class.
* Line number 17.

### Description:

This class utilized a fixed length 2D array, since this dimensional information if of use in many places in the whole project. But the array is initialzed with number as its size.

### Solution:

Introduced two integer constants rows and columns in the Human class, and it is defined as public so other classes can access this dimensional information.

### Explanation

Once the 2d array needs to adjust its size, we only need to update these two constants, while in the old style, we need to dig into the code the fix everywhere that hardcoded the array size.

============================================================

## Code Smell 4: [A lot of repated codes in serveral classes]

### Code Smell Category: [Data Clumps]

### List of classes and line numbers involved:

* Chicken class.
* Line number 7-10.

* Pig class.
* Line number 7-10.

* Human class.
* Line number 7-10.

### Description:

The three clasess Chicken, Pig and Human all represent farm objects and contain quite a lot of identical variables like r, c, and column.

### Solution:

We moved the definition of these variables into a super class called FarmObject, and make Chicken, Pig and Human classes all extend this super class, thus inheritance is deployed and data redundancy and clumps is eliminated.

### Explanation

In this way, the FarmObject will handle all the basic attributes for any FarmObject like coordinate information and color etc, the specific object, for example, Pig, will only need to add its specific attributes if needed, and only need to focus on its own logic in playing around in the farm for Pigs.

============================================================

## Fix the 2D Array:


### List of classes and line numbers involved:

* The Main Class
* Line number 55
* Line number 140-177
* Line number 208-235
### Description:

I've created an 1D ArrayList to store Java vanilla Objects without preset size. Then for each object that gets populated in the start(0 method, it is also added into the targetList variable of type ArrayList.

In this way, the targetList is no longer sparse since the row and column information is no longer needed here as index, since rows and columns information are already attributes of each farm Object. Similarly,in
line 208-235, the drawShape method, it simply needs to loop through the arraylist in one turn and draw each object.


============================================================

## Eliminate the Exception:

### List of classes and line numbers involved:

* The Chicken Class
* Line number 121-130

### Description:

The ArrayOutOfBoundsException occured basically since the integer r or c, which are used to track the current row or column index, goes out of the predefined 48*10 matrix limit, and the very correct timing when this occurs is when we try to move a Chicken, so the new row/column index calculated failed to take this predefined limit into account.

Thus, the solution is to to a double checking whenever the column or row index is updated. So if it goes beyond upper limit 47, then restart from 0; if it goes lower then 0, then restart from the upper limit 47.


============================================================

## New Farm Item

### The name of the class(es) that provide(s) functionality for your new farm item:
The class is another subclass of the FarmObject class and is named Cat.
It has all basic funcionalities like move or gets drawed on grahics and it also can steal eggs that layed by chickens.

### Description:

In the move() method of the Cat Class, it will use a random variable to make actions, when the random matches threshould, then it will check if there is any egg and get the egg then steals it.

============================================================
