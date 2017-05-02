### What is object oriented programming?

Object oriented programming (OOP) is an approach to software development based on objects and classes. This approach allows developers to organize software in collections of objects that consist on **data** and **behavior**.

This approach exists since the 80's, and almost all languages developrd after 1990 have object oriented features.

#### Main objectives of OOP

- Modularization - decompose the app into modules.

- Software re-use - new software and features can be built by reusing the code that already exists.

An object oriented language normally supports five main features:

- Classes

- Objects

- Classification

- Polymorphism

- Inheritance

### Class

A class is a blueprint of an object, it is the definition that says how every instance is created and how it behaves.

Think of a class as a *television* for example. It will have several features and properties:

- We don't have to open it to use it

- We have a set of controls to use it (either a remote or buttons directly on TV)

- We can still understand the concept of a TV, even if it is not used alone. (Ex: used with a DVD)

- It is complete when we bought it, external dependencies are well documented.

- It will not crash

If this TV was a real object oriented class, it had to:

- Provide a well defined, clear interface - Such as the remote or the buttons

- Represent a clear concept, being easy to recognize and to understand what is does.

- Be complete and well documented - Should have a plug and a clear explanation about it's features.

- The code should be robust, to not crash, and should handle his own "problems". - Such as the TV

As humans, we use a lot of "class based descriptions", what is a dog?

Classes allows the definition of pretty complex structures, and have two components:

- State/Data - The values the object has

- Actions/Behavior - The ways objects can interact with their data.

An instance of a class is called object.

### Object

As said, an object is an instance of a class, it is an entity that represents the class blueprint and has his own state. As if the class was the description and the object the concept it describes.

On the TV example, there is a clear way of defining what is a television, what it consists in and what it can do, that's the class.
The television object is a real world representation of that TV class description, and there can be a thousands of TVs that follow that class description.

Objects can be concrete (a file on the computer, an object in real world) and can also be abstract (a database structure, a connection to a database server).

![television][televisionObject]
[televisionObject]: http://www.eeng.dcu.ie/~ee553/ee402notes/html/figures/televisionObjects.gif


On the image, the top TV is the class description, every object below that are objects, instances of that class. Objects have their own identity and are independent.
The state is contained in each instance, if you change the channel in one of the TVs, it will not change on the others.

### Encapsulation

In object oriented languages, encapsulation is encouraged.

Encapsulation is the way of hiding implementation details, that show how things are done so we don't need to understand how the object works in order to use it. What we should understand is the interface that object provides.

Back to the TV example, the inner works of the TV are hidden from us, however, we are provided with a remote, that let us do what we want with the TV, providing a high level of abstraction. This way, we don't need to understand how the TV receives the signal and converts it in a picture to work with it.

![encapsulation][encapsulation]
[encapsulation]: http://www.eeng.dcu.ie/~ee553/ee402notes/html/figures/televisionObjects.gif

This approach has different advantages for different users:

**For another programmer (the user)**

- Only need to understand the interface

- Does not need to understand how the implementation was created

**For the developer (people who maintain the code)**

- Can change the implementation without warning the user and affecting the behaviour

To define the level of *hiding* of different methods or states in a class, we can define 3 different visibility methods:

- **public** - Describes the interface

- **private** - Describes implementation details

- **protected** - Describes implementation details that can be changed by class' children

Example:

```
// state
currentChannel = 1
volume = 50;

// interface
changeChannel()
updateVolume()

// implementation
decodeSignal()
displayPicture()
```

### Inheritance

If we have classes that have clear similarities between them, we can use inheritance to group them and provide a common representation of them.

This approach allows the developer to inherit the common parts and customize the parts that are different.

Question: What is a dog?

You may answer "a mammal that has 4 legs, barks, and has a shorter lifespan".

That's what we ask when we wanna decide if a class should inherit from another.

```
class Mammal {
    // state
    averageLifespan

    // methods
    communicate()
    breath() 
    walk()
}

class Dog extends Mammal {
    communicate() // defining that dogs communicate by bark
    walk() // defining that dogs walk with 4 legs
}
```

In the example above, the class dog inherits from the mammal class, those classes have now a child/parent relationship. If we have a different dog that does one of the things differently, that dog can also inherit from the Dog class.

One key question to check if your class structure is right is asking if "Class A **is a** Class B" or if "Class A **is a part** of Class B".

If Class A **is a** Class B, your question is right, it's a case where inheritance is well used. If Class A **is a part** of Class B, that's not an inheritance case, but a composition (or aggregation).

### Polymorphism

Polymorphism means "multiple forms", in OOP those forms refer to different forms of the same method. It was two forms **overriding** or **overloading**.

#### Overriding

When a child class redefines a base method, changing it's implementation, it is called **overriding**. So two classes with child/parent relationship can have different behaviours when the same method is called.

```
class Mammal {
    // state
    averageLifespan

    // methods
    communicate()
    breath() 
    walk()
}

class Dog extends Mammal {
    communicate() // defining that dogs communicate by bark
    walk() // defining that dogs walk with 4 legs
}
```

In this situation, Dog class would override the Mammal walk method, and implement it so Dog can walk in four legs.

#### Overloading

Overloading happens when the same class has two methods with the same name but they have different parameters.

```
class TV {
    channel()
    channel(x)
}
```

In the given example, you can call the method `channel` on the TV class with different parameters, getting different behaviours. For instance, when you call `channel` with no arguments, it shows you the channel you are in. On the other side, if you call it giving the desired channel as a parameter, it will change the TV channel to that one, this is a case of **overloading**.

### Abstract Class

An abstract class is a class that is meant to be inherited. It is something like an *incomplete class*. This class defines generic methods that **have to be** overridden by the child class. 

So, as the name says, an *abstract class* is a class that says that the child class **must have** some methods, but doesn't know how to implement them. Now we can see that our `Mammal` class should be an `abstract class`, as there is no "generic way" for a `Mammal` to breath or walk, every Mammal species has their own way.

```
abstract class Mammal {
    breath()
    walk()
    communicate()
}

class Dog extends Mammal {
  walk() {
    // walk with 4 legs
  }
    
  communicate() {
    // bark
  }

  //...
}
```
