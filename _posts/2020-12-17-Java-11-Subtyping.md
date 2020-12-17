Java subtyping in Java 11 has the following key rules:

# So what does an interface inherit if it extends another interface?

"The interface inherits,
from the interfaces it extends,
all members of those interfaces,
except for (i) fields,
classes,
and interfaces that it hides,
(ii) abstract methods and default methods that it overrides (§9.4.1),
(iii) private methods, and
(iv) static methods." - JLS 11 9.2

So: everything, except what it overrides or hides,
or what is private or static, apparently.

# And what does a class inherit if it implements an interface?

A class inherits default methods from interfaces it implements,
and does so if it doesn't override them.

"Each default method (§9.4.3) of a superinterface of the class
may optionally be overridden by a method in the class;
if not, the default method is typically inherited
and its behavior is as specified by its default body." - JLS 11 8.1.5

So how is this list different than 9.2's list of what an interface inherits from a superinterface?
A class only inherits methods, and only those that are non-private and non-static.

"A class does not inherit private or static methods from its superinterfaces." - JLS 11 8.4.8

# Finally, what does a class inherit if it extends another class?

Members that are accessible (public, etc.).


# Odd things about classes' use of interfaces

An interface that is a classes' grandparent's superinterface is not a superinterface of the class itself.
** DOES THIS MATTER? **


## Methods and Fields

Methods and fields are both inherited from a superclass, but only methods are inherited from a superinterface.
