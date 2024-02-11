# Structured Programming

>  Dijkstra’s rules of structured programming said that every function, and every block within a function, should have one entry and one
exit. 

* Following these rules means that there should only 
 - one return statement in a function, 
 - no break or continue statements in a loop,
 - and never, ever, any goto statements. 

 * So if you keep your functions small, then the occasional multiple return, break, or continue statement does no harm and can sometimes even be more expressive than the single-entry, single-exit rule.
 
 * On the other hand, goto only makes sense in large functions, so
it should be avoided.