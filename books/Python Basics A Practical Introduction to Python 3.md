# Python Basics A Practical Introduction to Python 3
- Class attributes are defined directly underneath the first line of the class and outside of any method definition. They must be assigned a value because they are created on a class instance without arguments to determine what their initial value should be
- You should use class attributes whenever a property should have the same initial value for all instances of a class. Use instance attributes for properties that must be specified before an instance is created.
- For user defined classes, the default behavior of the == operator is to compare the memory addresses of two objects and return True if the address is the same and False otherwise.
- You can access the parent class from inside a method of a child class by using the super() function.
