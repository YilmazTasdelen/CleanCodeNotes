# Arguments

> The ideal number of arguments for a function is
zero (niladic). Next comes one (monadic), followed
closely by two (dyadic). Three arguments (triadic)
should be avoided where possible. More than three
(polyadic) requires very special justification—and
then shouldn’t be used anyway.

* Arguments are even harder from a testing point of view. Imagine the difficulty of writing all the test cases to ensure that all the various combinations of arguments work properly.

Output arguments are harder to understand than input arguments. So output arguments often cause us to do a double-take. 

# Flag Arguments

* Flag arguments are ugly. Passing a boolean into a function is a truly terrible practice. It immediately complicates the signature of the method, loudly proclaiming that this function does more than one thing.


# Dyadic Functions

* A function with two arguments is harder to understand than a monadic function. For example, writeField(name) is easier to understand than writeField(output-Stream, name)

* There are times, of course, where two arguments are appropriate. For example,
Point p = new Point(0,0); is perfectly reasonable.

* Dyads aren’t evil, and you will certainly have to write them. However, you should be aware that they come at a cost and should take advantage of what mechanims may be available to you to convert them into monads

# Triads

*  I suggest you think very carefully before creating a triad.

# Argument Objects

*  When a function seems to need more than two or three arguments, it is likely that some of those arguments ought to be wrapped into a class of their own.

*  Reducing the number of arguments by creating objects out of them may seem like cheating, but it’s not. When groups of variables are passed together, the way x and y are in the example above, they are likely part of a concept that deserves a name of its own.

# Argument Lists

* Sometimes we want to pass a variable number of arguments into a function. Consider, for example, the String.format method:

        String.format("%s worked %.2f hours.", name, hours);

* If the variable arguments are all treated identically, as they are in the example above, then they are equivalent to a single argument of type List. By that reasoning, String.format is actually dyadic. Indeed, the declaration of String.format as shown below is clearly dyadic.

        public String format(String format, Object... args)

* So all the same rules apply. Functions that take variable arguments can be monads, dyads, or even triads. But it would be a mistake to give them more arguments than that.

        void monad(Integer... args);
        void dyad(String name, Integer... args);
        void triad(String name, int count, Integer... args);