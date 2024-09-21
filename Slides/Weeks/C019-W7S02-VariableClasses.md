{"title" : "Variable Size Objects","slidesid" : "W7S02"}# Variable Size Instances?```Array new: 10
> #(nil nil nil nil nil nil nil nil nil nil)``````Array new: 5
> #(nil nil nil nil nil)```Yes arrays can have different sizes# What You Will Learn- How to define variable size objects?- How to instantiate and access variable size objects?# Roadmap- **How to define variable size objects?**- How to instantiate and access variable size objects?# Variable Class DefinitionUse message `variableSubclass:` instead of `subclass:`Example```ArrayedCollection variableSubclass: #Array
	instanceVariableNames: ''
	classVariableNames: ''
	package: 'Collections-Sequenceable'```# Example Variable ClassExample```Object variableSubclass: #StrangePoint
        instanceVariableNames: 'x y'
        classVariableNames: ''
        package: 'Collections-Sequenceable'```- Instances of a variable class have a variable size \(indexed\) zone after named variables- Only one indexed instance variable per class \(always the last one\)# Roadmap- How to define variable size objects?- **How to instantiate and access variable size objects?**# Variable Class Instantiation and Index Access- Create instances with `new: max`- Access indexed values with `at:` and `at:put:`- First element starts at index 1- `size` returns the number of indexed instance variables```| a |
a := Array new: 4.
a at: 2 put: 'lulu'.
a at: 1
> nil
a at: 2 
> 'lulu'```# Classes with Different Shape- Classes with named instance variables   - `Counter` has an instance variable named `count`- Classes with a variable/indexed instance variable  - `Array` has only an indexed instance variable- Classes with some named instance variables **and** one indexed instance variable# Refining the Variable Part| Indexed | Named | Definition Method | Examples || --- | --- | --- | --- || No | Yes | #subclass:... | Color |  || Yes | No | #variableSubclass: | AdditionalMethodState |  || Yes | No | #variableByteSubclass: | ByteString |  || Yes | No | #variableWordSubclass: | Bitmap |  |Some methods related to class types: `isPointers`, `isBits`, `isBytes`, `isFixed`, `isVariable`# Constraints- Classes defined using `subclass:` can have any kind of subclasses- Classes defined using `variableSubclass:` can only have `variableSubclass:` subclasses# What You Should Know- How to define variable size objects?  - define a `variableSubclass:` with an indexed instance variable - How to instantiate variable size objects?  - use `new:`   - use `at:` and `at:put:` to access indexed values