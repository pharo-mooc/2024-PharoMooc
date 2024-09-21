{"title" : "Understanding the Implementation of ifTrue:ifFalse:","slidesid" : "W6S02"}# Yes ifTrue:ifFalse: is a message!```Weather isRaining
    ifTrue: [ self takeMyUmbrella ]
    ifFalse: [ self takeMySunglasses ]```- Conceptually `ifTrue:ifFalse:` is a message sent to an object: a boolean!- Heavily optimised by the compiler# Exercise- Propose an implementation of `ifTrue:ifFalse:`- You only have objects, messages and closures```   false ifTrue: [ 3 ] ifFalse: [ 5 ]
   -> 5

   true ifTrue: [ 3 ] ifFalse: [ 5 ]
   -> 3```# Implementing ifTrue:ifFalse:- Remember:   - `[ ]` freezes body execution   - `value` kicks execution of a frozen code- How to implement `ifTrue:ifFalse:`?- Remember Not and Or?# Implementation of ifTrue:ifFalse:Let the receiver decide!```True >> ifTrue: aTrueBlock ifFalse: aFalseBlock
   ^ aTrueBlock value``````False >> ifTrue: aTrueBlock ifFalse: aFalseBlock
   ^ aFalseBlock value```# Implementation of ifTrue:ifFalse:![](figures/BooleanIfTrueIfFalse.png width=110)# Conclusion- Sending a message selects the right method- Let the receiver decide- `[ ]` freezes computation and `value` forces execution