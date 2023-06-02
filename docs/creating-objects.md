## 1. Introduction to Objects

- **What are objects?**

    - In Java, an object is an instance of a class. It represents a particular entity or concept in your program.
    - An object has properties (known as fields or attributes) that describe its state, and it can perform actions (known as methods or behaviors).
    - **Example:** Consider a class called Car. An object of the Car class could represent a specific car, such as a "Toyota Camry." It would have properties like color, model, and speed, and it could perform actions like starting the engine or stopping.

- **Why do we use objects?**

    - Objects are essential in Java programming because they allow you to model real-world entities, encapsulate data and behavior, and build complex systems.
    - Objects promote code reusability, maintainability, and modularity by dividing functionality into smaller, manageable units.
    - Using objects enables you to apply object-oriented programming principles like encapsulation, inheritance, and polymorphism, leading to more organized and efficient code.
  
- **Key concepts: classes, objects, and instances**

    - **Class:** A class is a blueprint or template that defines the properties and behaviors of objects. It specifies what data an object will have (fields) and what operations it can perform (methods).
    - **Object:** An object is an instance of a class. It is created using the new keyword, and it occupies memory during the program's execution.
    - **Instance:** An instance refers to a specific object created from a class. It represents a unique occurrence of the class, with its own set of property values.
    - **Example:**
```
public class Car {

String color; // Property/Field

    public void startEngine() { // Action/Method
        System.out.println("Engine started!");
    }
}

public class Main {
    public static void main(String[] args) {
        Car myCar = new Car(); // Creating an object of the Car class
        myCar.color = "Red"; // Setting the color property of the car object
        myCar.startEngine(); // Calling the startEngine method on the car object
    }
}
```
In this example, the Car class represents the blueprint for creating car objects. The myCar object is an instance of the Car class, and it has its own color property and can perform the startEngine action.

## 2. Class and Object Relationship

- **Defining a class**

   - In Java, a class is a blueprint or template that defines the properties and behaviors (methods) of objects.
   - The class specifies the data fields (known as instance variables) and methods that objects of that class will have.
   - **Example:** Consider a class called Person that represents a person with properties like name and age, and methods like sayHello() and getAge().

```
public class Person {

  // Instance variables
  String name;
  int age;

  // Methods
  public void sayHello() {
      System.out.println("Hello, my name is " + name);
  }
  
  public int getAge() {
      return age;
  }
}
```
- **Creating objects from a class**

  - To create objects from a class, you use the new keyword followed by the class name and parentheses.
  - This process is called instantiation, where memory is allocated to hold the object.
  - Example: Creating objects of the Person class and accessing their properties and methods.

```
public class Main {

  public static void main(String[] args) {
    // Creating objects
    Person person1 = new Person();
    Person person2 = new Person();

    // Setting object properties
    person1.name = "John";
    person1.age = 25;
    
    person2.name = "Jane";
    person2.age = 30;
    
    // Accessing object properties and methods
    System.out.println(person1.name); // Output: John
    person2.sayHello(); // Output: Hello, my name is Jane
    System.out.println(person1.getAge()); // Output: 25
    
  }
}
```
- **Object references**

  - When you create an object, you can assign it to a variable, creating a reference to that object.
  - The reference variable allows you to access the object's properties and methods.
  - Multiple reference variables can refer to the same object, allowing you to have multiple ways to access and manipulate the object.
  - Example: Assigning multiple reference variables to the same Person object.


  ```
  public class Main {
    public static void main(String[] args) {
    Person person1 = new Person();
    Person person2 = person1; // Assigning person1 to person2
          person1.name = "John";
          System.out.println(person2.name); // Output: John
    }
  }
  ```

- **Object lifecycle: creation, manipulation, and destruction**

  - **Creation:** Objects are created using the new keyword and memory is allocated for the object. Constructors are invoked to initialize the object's state.
  - **Manipulation:** You can access and modify an object's properties and invoke its methods to perform actions or change its state.
  - **Destruction:** In Java, objects are automatically destroyed by the garbage collector when they are no longer referenced. The memory occupied by the object is freed.
**Example:** Illustrating the lifecycle of objects.
```
public class Person {
String name;

    public Person(String name) {
        this.name = name;
        System.out.println("Person " + name + " created!");
    }
    
    public void sayHello() {
        System.out.println("Hello, my name is " + name);
    }
    
    public void finalize() {
        System.out.println("Person " + name + " destroyed!");
    }
}

public class Main {
public static void main(String[] args) {
Person person1 = new Person("John"); // Creation
person1.sayHello(); // Manipulation

        person1 = null; // No reference to the object
        
        // Garbage collector may destroy the object, invoking the finalize method
    }
}
```


## 3. Object Creation

- **Instantiation**

  - In Java, instantiation refers to the process of creating an instance (or object) of a class.
  - When you instantiate an object, you allocate memory to hold that object and initialize its state.
  - Example: Suppose we have a class called Car representing a car object.

```
public class Car {
  private String brand;
  
      public void setBrand(String brand) {
          this.brand = brand;
      }
      
      public String getBrand() {
          return brand;
      }
}
```
- **The new keyword**

  - In Java, the new keyword is used to create a new instance of a class.
  - It dynamically allocates memory for the object and returns a reference to the newly created object.
  - Example: Creating an instance of the Car class using the new keyword.

 ``` Car myCar = new Car();```

- **Creating objects using constructors**

  - A constructor is a special method in a class that is used to initialize the object.
  - When you create an object using the new keyword, the constructor is automatically invoked to initialize the object's state.
  - Example: Adding a constructor to the Car class to initialize the brand property.
```
public class Car {
private String brand;

    public Car(String brand) {
        this.brand = brand;
    }
    
    public void setBrand(String brand) {
        this.brand = brand;
    }
    
    public String getBrand() {
        return brand;
    }
}
```
**Memory allocation for objects**

  -   When you instantiate an object, Java allocates memory to store the object and its instance variables. 
  - The memory allocation is done dynamically at runtime, and the size of the memory depends on the object's class and its instance variables.
  - Example: Creating objects and understanding memory allocation.


```
public class Main {

  public static void main(String[] args) {
    Car myCar = new Car("Toyota"); // Memory allocated for a Car object
    myCar.setBrand("Honda"); // Modifying the object's state
    String carBrand = myCar.getBrand(); // Accessing the object's state
   }
}
```

Understanding object instantiation is fundamental in Java programming. By using the new keyword and constructors, you can create objects and initialize their state. The memory allocation for objects is managed by the Java runtime environment, ensuring efficient memory usage.


## 4. Initializing Objects

- **Default initialization**

  - When an object is created, Java automatically initializes its instance variables with default values.
  - Default values depend on the data type:
  - For numeric types (e.g., int, double), the default value is 0.
  - For boolean types (boolean), the default value is false.
  - For reference types (e.g., objects), the default value is null.
  - Example:
```
public class Person {
  int age; // default value: 0
  boolean isEmployed; // default value: false
  String name; // default value: null
}

public class Main {
  public static void main(String[] args) {
    Person person = new Person();
    
    System.out.println(person.age); // Output: 0
    System.out.println(person.isEmployed); // Output: false
    System.out.println(person.name); // Output: null
  }
}\
```

- **Field initialization**

  - You can initialize instance variables directly at the point of declaration.
  - This allows you to provide specific initial values for the object's properties.
  - Example:

```
public class Person {
  int age = 25; // initialized to 25
  boolean isEmployed = true; // initialized to true
  String name = "John"; // initialized to "John"
}

public class Main {
  public static void main(String[] args) {
      Person person = new Person();
      System.out.println(person.age); // Output: 25
      System.out.println(person.isEmployed); // Output: true
      System.out.println(person.name); // Output: "John"
  }
}
```

- **Constructor initialization**

  - Constructors are special methods used to initialize an object's state.
  - You can define one or more constructors in a class to provide different ways of initializing the object.
  - Example:

```
public class Person {
  int age;
  boolean isEmployed;
  String name;
  
  public Person(int age, boolean isEmployed, String name) {
      this.age = age;
      this.isEmployed = isEmployed;
      this.name = name;
  }
}
  
public class Main {
    public static void main(String[] args) {
      Person person = new Person(30, true, "Jane");
      System.out.println(person.age); // Output: 30
      System.out.println(person.isEmployed); // Output: true
      System.out.println(person.name); // Output: "Jane"
    }
}

```
- **Static initialization blocks**

  - Static initialization blocks are used to initialize static variables in a class.
  - They are executed only once when the class is loaded into memory, before any objects of that class are created.
  - Example:
```
public class Person {
  static String country;
      static {
          country = "USA";
      }
  }

public class Main {
  public static void main(String[] args) {
    System.out.println(Person.country); // Output: "USA"
  }
}
```
## 5. Object References

- **Assigning object references**

  - In Java, object references are used to refer to objects in memory.
  - When you create an object, a reference variable is used to hold the memory address of the object.
  - Example:

```
  public class Person {
    String name;
    
        public Person(String name) {
            this.name = name;
        }
    }
    
    public class Main {
      public static void main(String[] args) {
        Person person1 = new Person("John"); // person1 holds the reference to the object
        Person person2 = person1; // person2 now refers to the same object as person1
    }
  }
```


- **Comparing object references**

  - Object references can be compared using the == operator to check if they refer to the same object.
  - The == operator compares the memory addresses of the objects.
  - Example:

```
public class Person {
String name;

    public Person(String name) {
        this.name = name;
    }
}

public class Main {
public static void main(String[] args) {
Person person1 = new Person("John");
Person person2 = new Person("John");

        System.out.println(person1 == person2); // Output: false
        
        Person person3 = person1;
        System.out.println(person1 == person3); // Output: true
    }
}
```

- **Object identity vs. object equality**

  - Object identity refers to whether two object references point to the same object in memory.
  - Object equality refers to whether two objects have the same values for their properties.
  - The equals() method is used to check for object equality based on the defined criteria.
  - Example:

```
public class Person {
  String name;
  
  public Person(String name) {
    this.name = name;
  }
  
  @Override
  public boolean equals(Object obj) {
    if (this == obj) {
        return true; // same memory address, same object
    }
  
    if (obj == null || getClass() != obj.getClass()) {
        return false; // different class or null object
    }
  
    Person otherPerson = (Person) obj;
    return Objects.equals(name, otherPerson.name); // compare names for equality
   }
  }
  
  public class Main {
    public static void main(String[] args) {
    Person person1 = new Person("John");
    Person person2 = new Person("John");
    
    System.out.println(person1.equals(person2)); // Output: true (based on name equality)
  }
}
```

## 6. Accessing Object Members

- Dot operator
- Accessing instance variables
- Invoking instance methods
- Accessing static members

## 7. Object Composition

- Creating objects that contain other objects
- Building complex object structures
- Relationships between objects: aggregation vs. composition

## 8. Object Destruction and Garbage Collection

- Object destruction process
- Garbage collection overview
- Object finalization
- System.gc() and finalizer methods

## 9. Object Cloning

- Creating a copy of an object
- Shallow vs. deep cloning
- Implementing the Cloneable interface
- Object cloning limitations and best practices

## 10. Object Serialization

- Saving objects to a file or network stream
- Object serialization process
- Implementing the Serializable interface
- Handling object versioning and compatibility

## 11. Singleton Pattern

- Creating a single instance of a class
- Ensuring global access to the instance
- Implementing the Singleton pattern
- Thread safety and lazy initialization
## 12. Object Pool Pattern

- Reusing existing objects
- Object pooling concept
- Implementing an object pool
- Managing object availability and resource usage

## 13. Object Comparison and Equality

- Comparing objects for equality
- The equals() method
- The hashCode() method
- Implementing custom equality for objects

## 14. Object-Oriented Design Principles

- Encapsulation
- Abstraction
- Inheritance
- Polymorphism

## 15. Object-Oriented Design Patterns

- Factory Pattern
- Builder Pattern
- Prototype Pattern
- Composite Pattern