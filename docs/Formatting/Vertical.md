# Vertical Formatting 

>  First of all, let’s be clear. Code formatting is important. It is too important to ignore and it is too important to treat religiously

> Let’s start with vertical size. How big should a source file be? In Java, file size is closely related to class size. We’ll talk about class size when we talk about classes.
 
# The Newspaper Metaphor

* Think of a well-written newspaper article. You read it vertically. At the top you expect a headline that will tell you what the story is about and allows you to decide whether it is something you want to read.

* The first paragraph gives you a synopsis of the whole story, hiding all the details while giving you the broad-brush concepts.

* As you continue downward, the details increase until you have all the dates, names, quotes, claims, and other minutia. We would like a source file to be like a newspaper article. 

* The name should be simple but explanatory. The name, by itself, should be sufficient to tell us whether we are in the right module or not. 

* The most parts of the source file should provide the high-level concepts and algorithms. Detail should increase as we move downward, until at the end we find the lowest level functions and details in the source file.

# Vertical Openness Between Concepts

 Each line represents an expression or a clause, and each group of lines represents a complete thought. Those thoughts should be separated from each other with blank lines. 

* There should be blank lines that separate the package declaration, the import(s), and each of the functions

# Vertical Density

If openness separates concepts, then vertical density implies close association. So lines of code that are tightly related should appear vertically dense

# Vertical Distance


Concepts that are closely related should be kept vertically close to each other. Clearly this rule doesn’t work for concepts that belong in separate files. But then closely related concepts should not be separated into different files unless you have a very good
reason. 

Indeed, this is one of the reasons that protected variables should be avoided. For those concepts that are so closely related that they belong in the same source file, their vertical separation should be a measure of how important each is to the understandability of the other.

 We want to avoid forcing our readers to hop around through our source
files and classes.

# Variable Declarations 

* Variables should be declared as close to their usage as possible. Because our functions are very short, local variables should appear a the top of each function,

* Control variables for loops should usually be declared within the loop statement, as in this cute little function from the same source.

* In rare cases a variable might be declared at the top of a block or just before a loop in a long-ish function. 

* Instance variables, on the other hand, should be declared at the top of the class. This should not increase the vertical distance of these variables, because in a well-designed class, they are used by many, if not all, of the methods of the class.

# Dependent Functions

If one function calls another, they should be vertically close,
and the caller should be above the caller, if at all possible. This gives the program a natural flow

# Conceptual Affinity 

Certain bits of code want to be near other bits. They have a certain
conceptual affinity. The stronger that affinity, the less vertical distance there should be between them

# Vertical Ordering

In general we want function call dependencies to point in the downward direction. That is, a function that is called should be below a function that does the calling. This creates a nice flow down the source code module from high level to low level. 