{
>>> 'a Delay(10000 msecs)'
   "Answer a String whose characters are a description of the receiver."
   ^ self printStringLimitedTo: 50000
   | limitedString |
   limitedString := String
                                        streamContents: [ :s | self printOn: s ]
                                        limitedTo: limit.
   limitedString size < limit ifTrue: [ ^ limitedString ].
   ^ limitedString , '...etc...'
>>> a Node
>>> an Apple
   "Append to the argument, aStream, a sequence of characters that identifies the receiver."
   | title |
   title := self class name.
   aStream
      nextPutAll: (title first isVowel ifTrue: [ 'an ' ] ifFalse: [ 'a ' ]);
      nextPutAll: title
> a Delay(1000 msecs)
   super printOn: aStream.
   aStream
      nextPutAll: '(';
      print: millisecondDelayDuration;
      nextPutAll: ' msecs)'
> false
   aStream nextPutAll: 'false'
> (1 to: 100)
1 to: 100 by: 3
> (1 to: 100 by: 3)
   aStream
      nextPut: $(;
      print: start;
      nextPutAll: ' to: ';
      print: stop.
   step ~= 1
      ifTrue: [ aStream nextPutAll: ' by: '; print: step ].
   aStream nextPut: $)
  "Answer another instance just like the receiver. Subclasses typically override postCopy. Copy is a template method in the sense of Design Patterns. So do not override it. Override postCopy instead. Pay attention that normally you should call postCopy of your superclass too."
    ^ self shallowCopy postCopy
  "Answer a copy of the receiver which shares the receiver's instance variables. Subclasses that need to specialize the copy should specialize the postCopy hook method."
  <primitive: 148>
  ...
  "I'm a hook method in the sense of Design Patterns TemplateHook/Methods. I'm called by copy. self is a shallow copy, subclasses should copy fields as necessary to complete the full copy"
  ^ self
   instanceVariableNames: 'contents'
   classVariableNames: ''
   package: 'Collections-Unordered'
   super postCopy.
   contents := contents copy
   "Must copy the associations, or later store will affect both the original and the copy"
   array := array 
               collect: [ :association |
                          association ifNotNil: [ association copy ] ]