# Dart Programming Lab

## About
In this lab, you'll practice fundamental Dart programming concepts that are essential for Flutter development. Each exercise is designed to reinforce concepts from the morning's lecture and demonstrate their practical application in Flutter app development.

## Setup
1. Open DartPad (https://dartpad.dev)
2. Create a new Dart file
3. Follow the exercises below

## Exercise 1: Variables and Types

### Why This Matters
Understanding Dart's type system is crucial for Flutter development because:
- Flutter widgets often require specific types for their properties
- Type safety helps catch errors before runtime, improving app stability
- Proper use of const can optimize Flutter's performance by allowing widget reuse

### Task
Create variables of different types and practice type inference.

```dart
// 1. Create variables using var, final, and const
// 2. Practice with different data types (int, double, String, bool)
// 3. Use type inference and explicit typing

void main() {
    // Your code here
    // Example:
    var name = 'John';
    final age = 25;
    const isStudent = true;
}
```

### Solution

```dart
void main() {
    // Using var for type inference
    var name = 'Alice';  // Dart infers String type
    var score = 95;      // Dart infers int type
    
    // Using explicit types
    String country = 'USA';
    int population = 331000000;
    
    // Using final for values that won't change after initialization
    final DateTime currentTime = DateTime.now();
    final double pi = 3.14159;
    
    // Using const for compile-time constants
    const bool isProduction = false;
    const double gravity = 9.81;
    
    // Printing values to verify
    print('Name: $name');
    print('Score: $score');
    print('Country: $country');
    print('Current Time: $currentTime');
    print('Is Production: $isProduction');
}
```

**Explanation:**
- `var` lets Dart infer the type, useful for local variables
- `final` is used for values that won't change but are computed at runtime
- `const` is for compile-time constants, which Flutter can optimize
- Explicit types improve code readability and self-documentation

## Exercise 2: Functions and Null Safety

### Why This Matters
Null safety and proper function design are critical in Flutter because:
- Flutter's widget constructors heavily use named parameters
- Null safety prevents common runtime errors in your Flutter apps
- Understanding parameter types helps when working with Flutter's widget callbacks

### Task
Create functions with different parameter types and return values, implementing null safety.

```dart
// Create these functions:
// 1. A function that takes nullable parameters
// 2. A function with named parameters
// 3. A function with required parameters
```

### Solution

```dart
// Function with nullable parameter and return type
String? getNullableName(String? input) {
    // Using null-aware operator
    return input?.toUpperCase();
}

// Function with named parameters (common in Flutter widgets)
double calculateArea({
    required double width,
    required double height,
    double scale = 1.0  // Optional parameter with default value
}) {
    return width * height * scale;
}

// Function with mixed parameter types
void displayUserInfo({
    required String name,
    int? age,
    String title = 'User'
}) {
    print('$title: $name');
    if (age != null) {
        print('Age: $age');
    }
}

void main() {
    // Testing the functions
    print(getNullableName('john'));  // Prints: JOHN
    print(getNullableName(null));    // Prints: null
    
    print(calculateArea(width: 10, height: 20));  // Prints: 200.0
    
    displayUserInfo(
        name: 'Alice',
        age: 30,
        title: 'Admin'
    );
}
```

**Explanation:**
- Nullable types (String?) allow variables to hold null values
- Named parameters with required keyword prevent null errors
- Default parameter values provide flexibility
- Null-aware operators (?.) safely handle potential null values

## Exercise 3: Classes and Objects

### Why This Matters
Object-oriented programming is fundamental to Flutter because:
- Every Flutter widget is a class
- Custom widgets are created by extending Flutter's widget classes
- State management often involves creating model classes

### Task
Create a Person class with properties and methods.

```dart
class Person {
    // 1. Add properties (name, age, email)
    // 2. Create a constructor
    // 3. Add methods
    // 4. Implement toString()
}
```

### Solution

```dart
class Person {
    // Properties
    final String name;
    final int age;
    String? email;  // Nullable property
    
    // Constructor with named parameters
    Person({
        required this.name,
        required this.age,
        this.email,
    });
    
    // Named constructor
    Person.guest() : 
        name = 'Guest',
        age = 0;
    
    // Method to check if person is adult
    bool isAdult() => age >= 18;
    
    // Method to update email
    void updateEmail(String newEmail) {
        email = newEmail;
    }
    
    // Override toString method
    @override
    String toString() {
        return 'Person(name: $name, age: $age, email: $email)';
    }
}

void main() {
    // Create person instances
    final person1 = Person(
        name: 'John Doe',
        age: 30,
        email: 'john@example.com'
    );
    
    final guest = Person.guest();
    
    // Use methods
    print(person1.toString());
    print('Is adult? ${person1.isAdult()}');
    
    person1.updateEmail('newemail@example.com');
    print(person1.toString());
}
```

**Explanation:**
- Properties use final when they shouldn't change after initialization
- Named constructors provide alternative ways to create objects
- Required parameters ensure necessary data is provided
- Methods encapsulate behavior, similar to widget methods in Flutter

## Level Up (Optional)

### Why This Matters
Advanced OOP concepts are essential in Flutter because:
- Flutter uses inheritance extensively (StatelessWidget, StatefulWidget)
- Interfaces help define contracts for widget behavior
- Abstract classes are common in Flutter's widget hierarchy

### Inheritance and Interfaces
Create a class hierarchy for different types of users in a system.

```dart
// Interface for permissions
abstract class Permissions {
    bool canEdit();
    bool canDelete();
}

// Abstract base class
abstract class User {
    final String id;
    final String name;
    
    User(this.id, this.name);
    
    // Abstract method
    void displayInfo();
}

// Student class implementing User
class Student extends User implements Permissions {
    final String grade;
    
    Student(String id, String name, this.grade) : super(id, name);
    
    @override
    void displayInfo() {
        print('Student: $name, Grade: $grade');
    }
    
    @override
    bool canEdit() => true;
    
    @override
    bool canDelete() => false;
}

// Teacher class implementing User
class Teacher extends User implements Permissions {
    final List<String> subjects;
    
    Teacher(String id, String name, this.subjects) : super(id, name);
    
    @override
    void displayInfo() {
        print('Teacher: $name, Subjects: $subjects');
    }
    
    @override
    bool canEdit() => true;
    
    @override
    bool canDelete() => true;
}

void main() {
    final student = Student('S1', 'Alice', 'A');
    final teacher = Teacher('T1', 'Mr. Smith', ['Math', 'Physics']);
    
    student.displayInfo();
    print('Student can edit: ${student.canEdit()}');
    
    teacher.displayInfo();
    print('Teacher can delete: ${teacher.canDelete()}');
}
```

**Explanation:**
- Abstract classes define a contract that child classes must fulfill
- Interfaces (abstract classes in Dart) define a set of methods that classes must implement
- Inheritance allows code reuse and polymorphism
- This pattern is similar to how Flutter's widget system is designed
