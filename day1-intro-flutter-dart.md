# Introduction to Flutter and Dart

## About
This lesson introduces students to Flutter framework and the Dart programming language. Students will learn about the advantages of Flutter for cross-platform development and get hands-on experience with Dart's core concepts.

## Flutter Architecture Overview

```mermaid
graph TD
    A[Flutter App] --> B[Flutter Framework]
    B --> C[Foundation Library]
    B --> D[Rendering Layer]
    B --> E[Widget Layer]
    B --> F[Material/Cupertino]
    C --> G[Platform Channels]
    G --> H[Android Platform]
    G --> I[iOS Platform]
    style A fill:#b7e3fc
    style B fill:#90caf9
    style C,D,E,F fill:#64b5f6
    style G fill:#42a5f5
    style H,I fill:#1e88e5
```

## Widget Tree Concept

```mermaid
graph TD
    A[MaterialApp] --> B[Scaffold]
    B --> C[AppBar]
    B --> D[Body: Container]
    D --> E[Column]
    E --> F[Text Widget]
    E --> G[Button Widget]
    E --> H[Image Widget]
    style A fill:#ffcdd2
    style B fill:#ef9a9a
    style C,D fill:#e57373
    style E fill:#ef5350
    style F,G,H fill:#f44336
```

## Development Environment Setup Flow

```mermaid
flowchart LR
    A[Install Flutter SDK] --> B[Set up IDE]
    B --> C[Configure Environment Variables]
    C --> D[Install Platform SDKs]
    D --> E[Create First Project]
    E --> F[Run Flutter Doctor]
    style A fill:#c8e6c9
    style B fill:#a5d6a7
    style C fill:#81c784
    style D fill:#66bb6a
    style E fill:#4caf50
    style F fill:#43a047
```

## Course Schedule

| Lesson | Time | Type | Skills |
|--------|------|------|---------|
| What is Flutter? | 30 min | Lecture | Understanding Flutter's architecture, widget tree, and hot reload |
| Development Environment Setup | 45 min | Code-Along | Installing Flutter SDK, setting up IDE, creating first project |
| Introduction to Dart | 45 min | Lecture | Dart syntax, variables, types, functions, and null safety |
| Dart Programming Lab | 60 min | Lab | Hands-on practice with Dart programming concepts |
| Break | 15 min | Break | |
| Object-Oriented Programming in Dart | 45 min | Lecture | Classes, inheritance, interfaces, and mixins |
| OOP Practice | 45 min | Code-Along | Building classes and implementing inheritance |
| **Total Morning Content** | **3.5 hours** | | |

## Dart Type System Overview

```mermaid
classDiagram
    class Object {
        +toString() String
        +hashCode int
        +operator ==() bool
    }
    class num {
        +operator +() num
        +operator -() num
    }
    class int {
        +operator >>() int
        +operator <<() int
    }
    class double {
        +toStringAsFixed() String
        +roundToDouble() double
    }
    Object <|-- num
    num <|-- int
    num <|-- double
```

## Object-Oriented Programming Concepts

```mermaid
classDiagram
    class Widget {
        +build() Widget
        +createElement() Element
    }
    class StatelessWidget {
        +build() Widget
    }
    class StatefulWidget {
        +createState() State
    }
    class State {
        +build() Widget
        +setState() void
    }
    Widget <|-- StatelessWidget
    Widget <|-- StatefulWidget
    StatefulWidget -- State
```

## Level Up Content

| Topic | Time | Skills |
|-------|------|---------|
| Dart Async Programming | 30 min | Understanding Future, async/await, and Streams |
| Flutter DevTools | 30 min | Using Flutter DevTools for debugging and performance optimization |

## Async Programming Visualization

```mermaid
sequenceDiagram
    participant App
    participant Future
    participant API
    App->>Future: async call
    Future->>API: request data
    API-->>Future: return data
    Future-->>App: complete with data
    Note over App,API: Async operations don't block the main thread
```

## Development Tools Ecosystem

```mermaid
mindmap
    root((Flutter Dev Tools))
        IDE Integration
            VS Code
            Android Studio
            IntelliJ
        Debugging
            Hot Reload
            Hot Restart
            Break Points
        Performance
            CPU Profiler
            Memory Profiler
            Network Inspector
        Widget Inspector
            Widget Tree
            Layout Explorer
            Property Explorer
```

## Key Takeaways

1. **Flutter's Advantages**
   - Single codebase for multiple platforms
   - Hot reload for rapid development
   - Rich widget library
   - Strong performance

2. **Dart Features**
   - Type safety
   - Null safety
   - Object-oriented
   - Async support

3. **Development Best Practices**
   - Use version control
   - Follow widget composition patterns
   - Implement proper state management
   - Write clean, maintainable code

---
© 2025 General Assembly
