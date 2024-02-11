# One Level of Abstraction per Function

> In order to make sure our functions are doing “one thing,” we need to make sure that the statements within our function are all at the same level of abstraction.


     // very high level of abstraction 
        getHtml();
    
     // intermediate level of abstraction   
     String pagePathName = PathParser.render(pagePath); 

     //  low level abstraction  
        .append("\n")

* Mixing levels of abstraction within a function is always confusing. Readers may not be able to tell whether a particular expression is an essential concept or a detail.


> Reading Code from Top to Bottom: The Stepdown Rule

We want the code to read like a top-down narrative.5 We want every function to be followed by those at the next level of abstraction so that we can read the program, descending one level of abstraction at a time as we read down the list of functions. I call this The Stepdown Rule