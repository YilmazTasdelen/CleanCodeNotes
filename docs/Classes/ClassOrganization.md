# Class Organization

>a class should begin with a list of variables. The order should be like this 

        * Public static constants
        * private static variables
        * private instance variables
        * public variable
        * Public functions should follow the list of variables.
        most of the case no good reason to have a public variable

 * Put the private var/const called by a public function right after the public function itself. This follows the stepdown rule and helps the program read like a newspaper article.



Encapsulation We like to keep our variables and utility functions private, but we’re not fanatic about it.

Sometimes we need to make a variable or utility function protected so that it can be accessed by a test.If a test in the same package needs to call a function or access a variable, we’ll make it protected or package scope. 

# Classes Should Be Small!

> The first rule of classes is that they should be small. 
With functions we measured size by counting physical lines. With classes we use a different measure. We count responsibilities.