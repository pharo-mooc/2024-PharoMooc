{
"title" : "Pharo Features (part)",
"author" : "S. Ducasse",
"slidesid" : "A0"
}


# Outline
Pharo benefits from an elegant design that enables a relatively simple implementation of many advanced programming techniques. 
- Advanced runtime reflection
- Resumable exceptions
- On demand stack reification
- DSL support
Thanks Pavel Krivanek for it


# Optional fusion

The optional fusion of a developed program and development environment
- In Pharo, the border between your program and IDE can be eliminated.
- You may directly use your code for a visual representation of your data structures during debugging, and easily modify the built-in tools to fit your needs, etc.

# Advanced run-time reflection

- Pharo exposes everything to the programmer. Every object in the system can be examined and changed with respect to the object encapsulation rules.
- Access all instances of a class.
- Enumerate all objects that have reference to some object.
- Switch references between objects.

# Advanced run-time reflection 2

- Pharo exposes everything to the programmer. Every object in the system can be examined and changed with respect to the object encapsulation rules.
- Access all instances of a classes.
- Enumerate all objects that have reference to some object.
- Switch references between objects.

# Pure object-oriented approach
- In Pharo, \** is an object.
- No static, no primitive types, no override, no overloading, no generics 
- This purity and uniformity in the system and language design makes Pharo clean and comfortable to learn.

# Software as objects
- Uses files for serialization of source code, but, by default, it does not use files to edit them. 
- It provides the tools to browse and modify the classes, methods, class comments and other program entities. 
- Pharo has a much better understanding of relations between them and allows easier navigation and refactorings.

# Simple language syntax
Complete syntax fits on one post card
- The language syntax has only six reserved words
- Since the grammar is LL\(1\), it is very fast to parse
- Easy to learn
- Pharo is designed for message passing without argument ambiguity

# Closure with non-local return: Foundation for DSL

# Fast resumable exceptions
- Pharo provides advanced exceptions system that can do things like resuming from a raised exception with providing an alternative result so your program can recover from failures.
- Their fast speed allows them to be used for clean information-flow mechanisms.

# Feels different and powerful
- http://www.pharo.org

# List
- pure oo and software as objects
- simple syntax
- optional fusion Environment/Language
- atomic object identity swapping
- Fast resumable exception
- Advanced run-time reflection
- Closure with non local returns
- LIve customizable object
- run-time class and object migration
- Advanced multi-platform JITing VM
- Easy call stack and Continuations
- Objects as methods
- AST level code execution
- Customisable 
- Traits
- First class customizable variables
- First class object layouts
- Green threads
- Customisable compiler
- Moldable tools
- Strong 
