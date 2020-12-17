Java subtyping in Java 11 has the following key rules:

# From the viewpoint of interfaces and classes
## So what does an interface inherit if it extends another interface?

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

## And what does a class inherit if it implements an interface?

"Each default method (§9.4.3) of a superinterface of the class
may optionally be overridden by a method in the class;
if not, the default method is typically inherited
and its behavior is as specified by its default body." - JLS 11 8.1.5

"A class does not inherit private or static methods from its superinterfaces." - JLS 11 8.4.8

"A class inherits from its direct superclass and direct superinterfaces all the non-private fields of the superclass and superinterfaces that are both accessible (§6.6) to code in the class and not hidden by a declaration in the class.  A private field of a superclass might be accessible to a subclass - for example, if both classes are members of the same class. Nevertheless, a private field is never inherited by a subclass." - JLS 11 8.3

## Finally, what does a class inherit if it extends another class?

"Only members of a class that are declared protected or public are inherited by subclasses declared in a package other than the one in which the class is declared.  Constructors, static initializers, and instance initializers are not members and therefore are not inherited." - JLS 11 8.2

"A class inherits from its direct superclass and direct superinterfaces all the non-private fields of the superclass and superinterfaces that are both accessible (§6.6) to code in the class and not hidden by a declaration in the class.  A private field of a superclass might be accessible to a subclass - for example, if both classes are members of the same class. Nevertheless, a private field is never inherited by a subclass." - JLS 11 8.3

"A class C inherits from its direct superclass all concrete methods m (both static and instance) of the superclass for which all of the following are true:"
and an unsurprising list of qualifications. - JLS 11 8.4.8

"A class C inherits from its direct superclass and direct superinterfaces all abstract and default (§9.4) methods m for which all of the following are true:" - JLS 11 8.4.8


# From the Viewpoint of Members

## Fields

Roughly, fields are always inherited if not hidden.  But always hidden if names overlap.  When hidden, the type, staticness, and access modifier don't matter.

A hidden field can be accessed with "super" or with an explicit type qualification.

## Methods

Roughly, methods are always inherited from a class if not hidden or overridden, and always inherited from a superinterface if not static and not overridden.

To override or hide, the overriding or hiding method must have the same parameters, a same or broader access class, a same or narrower set of "throws",
and a same or subtyped return value.

Non-static methods override.  Static methods hide static methods of superclasses.
If a static method tries to hide a static method of an interface, it isn't really hiding it,
so has no restrictions on return type, etc.

## Types

Not sure yet.  "To do".
