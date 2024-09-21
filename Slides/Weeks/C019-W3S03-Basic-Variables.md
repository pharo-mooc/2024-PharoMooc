{
   | c |
   c := Counter new.
   ...
   instanceVarNames: 'x y'
   instanceVarNames: 'count'
  "Answer a number that is the cross product of the receiver and 
  the argument, aPoint."

  ^ (x * aPoint y) - (y * aPoint x)
Transcript show: 'hello world'.
Transcript cr.
   instanceVariableNames: 'codes combined'
   classVariableNames: 'Compositions Decompositions Diacriticals'
   package: 'Kernel-BasicObjects'