# Design Patterns

This repo follows the GoF book to explore and exercise design patterns.

## Principles

1. Program to an interface, not an implementation
1. Favor object composition over class inheritance


## Intro

### Mixin

A *Mixin* class is a class that's intended to provide an optional inteface or functionality to other classes.

### Class vs Interface

The class defines the objects internal state and the implementation of its operations.

An object's type only refers to its interface - the set of requests to which it can respond.

An object can have many types, and objects of different classes can have the same type.

When we say that an object is an instance of a class, we imply that the object supports the interface defined by the class.

Subclass (class inheritance) and subtyping (interface inheritance) is different. Class inheritance is a mechanism for code and representation sharing. Subtyping describes when an object can be used in place of another.

It's easy to confuse these two since in languages like C++, the standard way to inherit an inteface is to hnherit publicly from a class that has (pure) virtual member functions.

### Benefits of programming to interface not implementation

* Clients remain unaware of the specific types of objects they use, as long as the objects adhere to the interface that client expect.
* Clients remain unaware of the classes that implements the objects. Clients only know about the abstract class(es) defining the interface.

### Inheritance vs Composition

Reuse by subclassing is often referred to as white-box reuse. With inheritance, the internals of parent classes are visible to subclasses.

Reuse by composition requires that the objects being composed have well-defined interfaces. This style of reuse is called black-box reuse, because no internal details of objects are visible.

Disadvantages of subclassing:

* inheritance happens at compile time. Cannot be changed at runtime
* Child class is bonded with parent's implementation. It breaks encapsulation.

Composition requires carefully designed interfaces and can keep classes small.

### Delegation

Example: a class Window should have a Rectangle instead of being subclass of Rectangle. When calling window.area(), it delegates to this.rectangle.area().

The advantage is that it makes easy to compose behaviors at runtime and to change the wayt they are composed.

### Aggregation vs acquaintance

Aggregation means one object owns another object. Acquaintance not, it's just using it.