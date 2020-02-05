# Markdown

Markdown is a plain-text file format. There are lots of programming tools that use Markdown, and it's useful and
easy to learn. Hash marks (the number sign) indicate headers. Asterisks indicate lists.

# List of code smells

## Code Smell 1: [Main class has a very long start method]

### Code Smell Category: [Long Method]

### List of classes and line numbers involved:

* Class Main
* Line number 43-108.

### Description:

This method contains a very large number of lines of codes(nearly 90 lines). And a lot of codes are simply repated logic with different values applied.

### Solution:

For the line 50-75 in the original Main.java, they are simply doing some data populating work, thus I need to take them out and create a separate method containing these lines.

### Explanation

Firstly, I group these lines of code into a standalone method named populateFarmObjects().
Secondly, I only need to make a simple call to populateFarmObjects() now in the start() method.
Finally, there are several repeated code in the populateFarmObjects() as well as some codes that are being overriden by later codes, thus I removed those unnecessary code as well.

============================================================

## Code Smell 2: [Write the code smell name]

### Code Smell Category: [Write the code smell category name]

### List of classes and line numbers involved:

* [Write a class and list of line numbers, one class per asterisk, that describe the smell]

### Description:

[In your own words, explain how the description of the code smell applies to this particular code.]

### Solution:

[In your own words, explain how you might solve this code smell:
how would you refactor the code?]

### Explanation

[How does your solution get rid of the code smell? Write your explanation here.]

============================================================

## Code Smell 3: [Write the code smell name]

### Code Smell Category: [Write the code smell category name]

### List of classes and line numbers involved:

* [Write a class and list of line numbers, one class per asterisk, that describe the smell]

### Description:

[In your own words, explain how the description of the code smell applies to this particular code.]

### Solution:

[In your own words, explain how you might solve this code smell:
how would you refactor the code?]

### Explanation

[How does your solution get rid of the code smell? Write your explanation here.]

============================================================

## Code Smell 4: [Write the code smell name]

### Code Smell Category: [Write the code smell category name]

### List of classes and line numbers involved:

* [Write a class and list of line numbers, one class per asterisk, that describe the smell]

### Description:

[In your own words, explain how the description of the code smell applies to this particular code.]

### Solution:

[In your own words, explain how you might solve this code smell:
how would you refactor the code?]

### Explanation

[How does your solution get rid of the code smell? Write your explanation here.]

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


### Description:

[Explain how your new farm item interacts with the rest of the farm.]

============================================================
