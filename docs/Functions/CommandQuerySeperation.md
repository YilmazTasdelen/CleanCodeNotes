# CommandQuerySeperation

> Functions should either do something or answer something, but not both. 

* Either your function should change the state of an object, or it should return some information about that object.

* Doing both often leads to confusion. Consider, for example, the following
function:
        
        public boolean set(String attribute, String value);

* This function sets the value of a named attribute and returns true if it is successful and false if no such attribute exists. This leads to odd statements like this:

        if (set("username", "unclebob"))...

* Imagine this from the point of view of the reader. What does it mean? Is it asking whether the “username” attribute was previously set to “unclebob”? Or is it asking whether the “username” attribute was successfully set to “unclebob”? 

* It’s hard to infer the meaning from
the call because it’s not clear whether the word “set” is a verb or an adjective. 