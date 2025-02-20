# Dart Programming Lab

In this lab, you'll practice fundamental Dart programming concepts including variables, functions, classes, and null safety. These exercises will help reinforce the morning's lecture content and prepare you for Flutter development.

## Setup

1. Open [DartPad](https://dartpad.dev)
2. Create a new Dart file
3. Follow the exercises below

## Exercise 1: Variables and Types

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

### Expected Output
Demonstrate proper use of variables and type system

## Exercise 2: Functions and Null Safety

### Task
Create functions with different parameter types and return values, implementing null safety.

```dart
// Create these functions:
// 1. A function that takes nullable parameters
// 2. A function with named parameters
// 3. A function with required parameters

String? getNullableName(String? input) {
    // Your code here
}

double calculateArea({
    required double width,
    required double height
}) {
    // Your code here
}
```

## Exercise 3: Classes and Objects

### Task
Create a Person class with properties and methods.

```dart
class Person {
    // 1. Add properties (name, age, email)
    // 2. Create a constructor
    // 3. Add methods
    // 4. Implement toString()
}

void main() {
    // Create instances of Person
    // Call methods on the instances
}
```

## Level Up (Optional)

### Inheritance and Interfaces
Create a class hierarchy for different types of users in a system.

```dart
// Create:
// 1. An abstract User class
// 2. Student and Teacher classes that extend User
// 3. An interface for permissions

abstract class User {
    // Your code here
}
```

---
© 2025 General Assembly
