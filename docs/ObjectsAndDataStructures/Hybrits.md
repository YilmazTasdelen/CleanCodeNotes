# Hybrits

* This confusion sometimes leads to unfortunate hybrid structures that are half object and half data structure.

They have functions that do significant things, and they also have either public variables or public accessors and mutators that, for all intents and purposes, make the private variables public, tempting other external functions to use those variables the way a procedural program would use a data structure.

* Such hybrids make it hard to add new functions but also make it hard to add new data structures. 

They are the worst of both worlds. Avoid creating them. They are indicative of a muddled design whose authors are unsure of—or worse, ignorant of—whether they need protection from functions or types.