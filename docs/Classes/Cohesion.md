# Cohesion

Classes should have a small number of instance variables. Each of the methods of a class should manipulate one or more of those variables. In general the more variables a method manipulates the more cohesive that method is to its class. A class in which each variable is used by each method is maximally cohesive. 


			public class Stack {
			private int topOfStack = 0;
			List<Integer> elements = new LinkedList<Integer>();
			public int size() {
			return topOfStack;
			}
			public void push(int element) {
			topOfStack++;
			elements.add(element);
			}
			public int pop() throws PoppedWhenEmpty {
			if (topOfStack == 0)
			throw new PoppedWhenEmpty();
			int element = elements.get(--topOfStack);
			elements.remove(topOfStack);
			return element;
			}
			}

This is a very cohesive class. Of the three methods only size() fails to use both the variables. 

# Maintaining Cohesion Results in Many Small Classes

So breaking a large function into many smaller functions often gives us the opportunity to split several smaller classes out as well. This gives our program a much better organization and a more transparent structure.

when you do that , the first thing you might notice is that the program got a lot longer. It went from a little over one page to nearly three pages in length. There are several reasons for this growth.

 First, the refactored program uses longer, more descriptive variable names.

Second, the refactored program uses function and class declarations as a way to add commentary to the code. 

Third, we used whitespace and formatting techniques to keep the program readable.

* We want to structure our systems so that we muck with as little as possible when we update them with new or changed features. In an ideal system, we incorporate new features by extending the system, not by making modifications to existing code. 
