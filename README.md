
# Relationship-in-OOPS

OOPS relies on four fundamental relationships between classes: Inheritance, Association, Composition, and Aggregation. These relationships help us model complex systems and facilitate the creation of robust, maintainable, and scalable software.


## JAVA

1) IS-A :
The "is a" relationship in Java is a fundamental concept in object-oriented programming (OOP), achieved through inheritance. Inheritance allows one class (subclass or child class) to inherit attributes and methods from another class (superclass or parent class), denoted by the keyword 'extends'.

```bash
class Animal {
    void eat() {
        System.out.println("Animal is eating");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog is barking");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog();
        myDog.eat();  // Inherited method from Animal
        myDog.bark(); // Method specific to Dog
    }
}

```
2) HAS-A :
In Java, the "has a" relationship refers to composition, where one class contains an instance of another class as a member variable. This relationship is established by creating an instance of the contained class within the containing class.

```bash
class Pen {
    // Pen implementation
}

class Student {
    private Pen pen; // Student "has a" Pen

    public Student() {
        this.pen = new Pen(); // Composition: Student has a Pen
    }
}

public class Main {
    public static void main(String[] args) {
        Student student = new Student();
    }
}


```
3) USES-A :
In Java, the "uses-a" relationship typically refers to association, where one class uses objects of another class as part of its functionality.

```bash
class Car {
    void drive(Engine engine) {
        // Car "uses-a" Engine to drive
        engine.start();
        // Other driving logic
        engine.stop();
    }
}

class Engine {
    void start() {
        System.out.println("Engine starting...");
    }

    void stop() {
        System.out.println("Engine stopping...");
    }
}

public class Main {
    public static void main(String[] args) {
        Car myCar = new Car();
        Engine myEngine = new Engine();
        myCar.drive(myEngine); // Car "uses-a" Engine to drive
    }
}


```


## JAVASCRIPT

1) IS-A :

```bash
var Animal = {
    sleep: function() {
        console.log("Zzz...");
    }
};

var Dog = Object.create(Animal);
Dog.bark = function() {
    console.log("Woof!");
};

var myDog = Object.create(Dog);
myDog.bark(); 
myDog.sleep(); 


```
2) HAS-A :

```bash
var Engine = {
    start: function() {
        console.log("Engine started");
    },
    stop: function() {
        console.log("Engine stopped");
    }
};

var Car = {
    engine: Engine, 
    drive: function() {
        this.engine.start();
        console.log("Car is driving");
    },
    stop: function() {
        console.log("Car stopped");
        this.engine.stop();
    }
};

Car.drive();
Car.stop(); 



```
3) USES-A :

```bash
var Logger = {
    log: function(message) {
        console.log("Log: " + message);
    }
};

var UserManager = {
    logger: Logger, 
    createUser: function(username) {
        this.logger.log("Creating user: " + username);
    },
    deleteUser: function(userId) {
        this.logger.log("Deleting user with ID: " + userId);
    }
};

UserManager.createUser("JohnDoe"); 
UserManager.deleteUser(123);    



```

