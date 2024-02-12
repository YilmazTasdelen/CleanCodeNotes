# UncheckedExceptions

> What price? The price of checked exceptions is an Open/Closed Principle violation.

* If you throw a checked exception from a method in your code and the catch is three levels above, you must declare that exception in the signature of each method between you and the catch. 

* This means that a change at a low level of the software can force signature changes on many higher levels. The changed modules must be rebuilt and redeployed, even though nothing they care about changed. 