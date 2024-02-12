# Data Object Anti-Symmetry

> These two examples show the difference between objects and data structures. Objects hide their data behind abstractions and expose functions that operate on that data. Data structure expose their data and have no meaningful functions.

> Notice the complimentary nature of the two definitions. They are virtual opposites. This difference may seem trivial, but it has far-reaching implications.

        public class Point {
         public double x;
         public double y;
        }

        public interface Point {
         double getX();
         double getY();
         void setCartesian(double x, double y);
         double getR();
         double getTheta();
         void setPolar(double r, double theta);
        }

> Procedural code (code using data structures) makes it easy to add new functions without changing the existing data structures. OO code, on the other hand, makes it easy to add new classes without changing existing functions.

The complement is also true:

> Procedural code makes it hard to add new data structures because all the functions must change. OO code makes it hard to add new functions because all the classes must change.

* In any complex system there are going to be times when we want to add new data types rather than new functions. For these cases objects and OO are most appropriate. On the other hand, there will also be times when we’ll want to add new functions as opposed to data types. In that case procedural code and data structures will be more appropriate.

* Mature programmers know that the idea that everything is an object is a myth. Sometimes you really do want simple data structures with procedures operating on them