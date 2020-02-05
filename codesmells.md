# Markdown

Markdown is a plain-text file format. There are lots of programming tools that use Markdown, and it's useful and
easy to learn. Hash marks (the number sign) indicate headers. Asterisks indicate lists.

# List of code smells

## Code Smell 1: [Write the code smell name]

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

* The Chicken Class
* Line number 121-130
### Description:

[In your own words, explain how you eliminated the 2D array.]


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
