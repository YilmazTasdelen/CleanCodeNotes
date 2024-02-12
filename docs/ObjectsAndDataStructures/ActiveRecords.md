# Active Records

> Active Records are special forms of DTOs. They are data structures with public (or beanaccessed) variables; but they typically have navigational methods like save and find.

> Typically these Active Records are direct translations from database tables, or other data sources.

* Unfortunately we often find that developers try to treat these data structures as though they were objects by putting business rule methods in them. 

* This is awkward because it creates a hybrid between a data structure and an object. 

* The solution, of course, is to treat the Active Record as a data structure and to create separate objects that contain the business rules and that hide their internal data.