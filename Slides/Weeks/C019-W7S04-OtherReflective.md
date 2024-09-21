{
pt1 := 0@0.
pt2 := pt1.
pt3 := 100@100.
pt1 become: pt3.
self assert: pt2 = (100@100). 
self assert: pt3 = (0@0).
self assert: pt1 = (100@100)
pt1 := 0@0.
pt2 := pt1.
pt3 := 100@100.
pt1 becomeForward: pt3.
self assert: pt1 = (100@100).
self assert: pt1 == pt2.
self assert: pt2 == pt3.
   "Change the class of anInstance to me. Returns the class rather than the modified instance"

  super initialize.
  self superclass: Object.
  self methodDict: self emptyMethodDictionary.
  self setFormat: Object format.
behavior := Behavior new.
behavior superclass: Model.
behavior setFormat: Model format.
model := Model new.
model primitiveChangeClassTo: behavior new. 
self assert: model class = behavior.
self assert: model class superclass = Model.
behavior compile: 'foo ^ 2'.
self assert: model foo = 2.
self should: [Model new foo] raise: MessageNotUnderstood
logClass := Behavior new. 
logClass superclass: Set;
   setFormat: Set format.
logClass compile: 'add: anObject
      Transcript show: ''adding '', anObject printString; cr.
      ^ super add: anObject'.
set := Set new.
set add: 1.
set class. 
set primitiveChangeClassTo: logClass basicNew. 
set add: 2.