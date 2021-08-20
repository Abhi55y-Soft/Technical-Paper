# OOP

As a Software engineer trainee, I should know the word **OOP** if I want to progress in the field of _software development_. Also, Understand its existence in real life. This is my short technical article on **Object Oriented Programming**.
Object Oriented Programming is a programming paradigm, which is based on the concept of Objects, and it contains data.
There are four Basic Principles of OOP Encapsulation, Abstraction, Inheritance, and Polymorphism, which will I'm going to explain in this article.

## Encapsulation

As the definition says, enclosing something in a capsule, the meaning of encapsulation in OOP is encapsulating data by default.
Encapsulation is, containing all important information inside of an object, and only exposing selected information to the outside world. Attributes and behaviors are defined by code inside the class template. It helps in emulating real-world objects.
For Example, If we are writing code for a Stack, we would have a stack class, which would contain all the information about push pop top — and all its methods inside a single entity.

```javascript
class Stack {
  constructor() {
    this.data = [];
    this.top = 0;
  }
  push(element) {
    this.data[this.top] = element;
    this.top = this.top + 1;
  }
  length() {
    return this.top;
  }
  peek() {
    return this.data[this.top - 1];
  }
  isEmpty() {
    return this.top === 0;
  }
  pop() {
    if (this.isEmpty() === false) {
      this.top = this.top - 1;
      return this.data.pop(); // removes the last element
    }
  }
  print() {
    var top = this.top - 1; // because top points to index where new element to be inserted
    while (top >= 0) {
      // print upto 0th index
      console.log(this.data[top]);
      top--;
    }
  }
  reverse() {
    this._reverse(this.top - 1);
  }
  _reverse(index) {
    if (index != 0) {
      this._reverse(index - 1);
    }
    console.log(this.data[index]);
  }
}
```

All the attributes of the stack are “encapsulated” together inside a class. Encapsulation provides the security like to access any information of stack you should deal with object. It also protects developers from making mistakes and all the code is hidden inside the class only public methods are accessible by outside developers.
Encapsulation prevents duplication of code, Inconsistency. Also, provides high maintainability.

## Abstraction

Abstraction deals with the quality of ideas rather than events, this is what a good software or product needs to have to give a better user experience. Abstraction means is to hide all the complexities and implementations from the users, to make it easier for them to use it.
For example, if the user is using a camera, they don’t need to know how the mechanism is working, but they can use functionality, to capture photos.
Abstraction hides complexity from the user, it provides high maintainability, and we can add functionality without impacting others.

## Inheritance

Just like we inherit genes, features from our parents, it is possible to inherit attributes, methods, data from one class to another.
For example, the class named "Model" will inherit the methods from the "Car" class:

```javascript
class Car {
  constructor(brand) {
    this.carname = brand;
  }
  present() {
    return "I have a " + this.carname;
  }
}

class Model extends Car {
  constructor(brand, mod) {
    super(brand);
    this.model = mod;
  }
  show() {
    return this.present() + ", it is a " + this.model;
  }
}
```

The super() method refers to the parent class. By calling the super() method in the constructor method, we call the parent's constructor method and get access to the parent's properties and methods.

Inheritance helps separate common functionality and fields so that they can be reused across many other classes cleanly. It also Avoids code redundancy.

## Polymorphism

Polymorphism means to have a function with the same name performing a different task. In real life, a woman can have different roles. She can be a mother, an employee, and a wife at the same time. The same woman will perform different functions depending on her particular role at the moment. This is the concept of polymorphism, being able to take on different forms.
For example, a class that calculates the area and perimeter of different shapes.

```javascript
class Shape {
  area() {
    return 0;
  }
  perimeter() {
    return 0;
  }
  toString() {
    return Object.getPrototypeOf(this).constructor.name;
  }
}

class Circle extends Shape {
  constructor(r) {
    super();
    this.radius = r;
  }

  area() {
    return Math.PI * this.radius ** 2;
  }

  perimeter() {
    return Math.PI * this.radius * 2;
  }
}

class Rectangle extends Shape {
  constructor(w, h) {
    super();
    this.width = w;
    this.height = h;
  }

  area() {
    return this.width * this.height;
  }
  perimeter() {
    return 2 * (this.width + this.height);
  }
}

const shapes = [new Circle(3), new Rectangle(2, 3)];

console.log(cumulateShapes(shapes));
```

Polymorphism presents the ability to perform different actions using the same method signature. And it helps keep the code cleaner.

### Conclusion

**Object Oriented Programming** requires deep thinking about structure and planning at the beginning of the coding. Analyze and break the requirements into simple classes that can be used by the objects. Overall, implementing OOP allows for better data structures and reusability, saving time in the long run.

### References

- https://stackoverflow.blog/2020/09/02/if-everyone-hates-it-why-is-oop-still-so-widely-spread/
- https://medium.com/swlh/applying-oop-in-real-world-applications-495c8ee4d946
