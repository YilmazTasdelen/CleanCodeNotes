# Class Names

* Methods should have verb or verb phrase names like postPayment, deletePage, or save.
Accessors, mutators, and predicates should be named for their value and prefixed with get,
set, and is according to the javabean standard.. 

* Avoid words like Manager, Processor, Data, or Info in the name
of a class. A class name should not be a verb.

        string name = employee.getName();
        customer.setName("mike");
        if (paycheck.isPosted())...

* When constructors are overloaded, use static factory methods with names that
describe the arguments. For example,
        Complex fulcrumPoint = Complex.FromRealNumber(23.0);

is generally better than

        Complex fulcrumPoint = new Complex(23.0);

Consider enforcing their use by making the corresponding constructors private.