# Dont Return Null

        public void registerItem(Item item) {
         if (item != null) {
         ItemRegistry registry = peristentStore.getItemRegistry();
         if (registry != null) {
         Item existing = registry.getItem(item.getID());
         if (existing.getBillingPeriod().hasRetailOwner()) {
         existing.register(item);
          }
         }
        }
       }


It’s easy to say that the problem with the code above is that it is missing a null check, but in actuality, the problem is that it has too many.

If you are tempted to return null from a method, consider throwing an exception or returning a SPECIAL CASE object instead.

If you are calling a null-returning method from a third-party API, consider wrapping that method with a method that either throws an exception or returns a special case object.


In many cases, special case objects are an easy remedy. Imagine that you have code like this:
```
List<Employee> employees = getEmployees();
if (employees != null) {
 for(Employee e : employees) {
 totalPay += e.getPay();
 }
}
```
Right now, getEmployees can return null, but does it have to? If we change getEmployee so that it returns an empty list, we can clean up the code:
```
List<Employee> employees = getEmployees();
for(Employee e : employees) {
 totalPay += e.getPay();
}
```
Fortunately, Java has Collections.emptyList(), and it returns a predefined immutable list that we can use for this purpose:
```
public List<Employee> getEmployees() {
 if( .. there are no employees .. )
 return Collections.emptyList();
}
```
If you code this way, you will minimize the chance of  NullPointerExceptions and your code will be cleaner

# Don’t Pass Null
Returning null from methods is bad, but passing null into methods is worse. Unless you are working with an API which expects you to pass null, you should avoid passing null in your code whenever possible