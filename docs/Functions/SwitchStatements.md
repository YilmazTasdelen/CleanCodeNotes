# Switch statements 

 Unfortunately we can’t always avoid switch statements, but we can make sure that each switch
statement is buried in a low-level class and is never repeated. We do this, of course, with
polymorphism.


        public Money calculatePay(Employee e)
            throws InvalidEmployeeType {
             switch (e.type) {
                case COMMISSIONED:
                    return calculateCommissionedPay(e);
                case HOURLY:
                    return calculateHourlyPay(e);
                case SALARIED:
                    return calculateSalariedPay(e);
                default:
                    throw new InvalidEmployeeType(e.type);
             }
        }

* First, it’s large, and when new
employee types are added, it will grow. 

* Second, it very clearly does more than one thing.

* Third, it violates the Single Responsibility Principle (SRP) because there is more than one
reason for it to change. 

* Fourth, it violates the Open Closed Principle (OCP) because it must change whenever new types are added. 

* But possibly the worst problem with this function is that there are an unlimited number of other functions that will have the same structure. For example we could have

        isPayday(Employee e, Date date),
        or
        deliverPay(Employee e, Money pay),
 
 All of which would have the same deleterious structure.

> The solution to this problem (see Listing 3-5) is to bury the switch statement in the
basement of an ABSTRACT FACTORY,and never let anyone see it.

* My general rule for switch statements is that they can be tolerated if they appear
only once, are used to create polymorphic objects, and are hidden behind an inheritance.

			public abstract class Employee {
				
				public abstract boolean isPayday();
				public abstract Money calculatePay();
		
			public abstract void deliverPay(Money pay);
			}
			
			-----------------
			public interface EmployeeFactory {
				public Employee makeEmployee(EmployeeRecord r) throws InvalidEmployeeType;
			}
			
			-----------------
			public class EmployeeFactoryImpl implements EmployeeFactory {
			
			public Employee makeEmployee(EmployeeRecord r) throws InvalidEmployeeType {
				switch (r.type) {
					case COMMISSIONED:
						return new CommissionedEmployee(r) ;
					case HOURLY:
						return new HourlyEmployee(r);
					case SALARIED:
						return new SalariedEmploye(r);
					default:
					throw new InvalidEmployeeType(r.type);
				}
			  }
			}