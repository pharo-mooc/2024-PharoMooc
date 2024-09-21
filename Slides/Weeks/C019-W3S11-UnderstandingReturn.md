{
   "Answer the receiver multipled by itself."
   ^ self * self
   self players
      at: 'tileAction'
      put: ...
   self players
      at: 'tileAction'
      put: ...
   ^ self       "<-- optional"
   x + 33.
   x + 2 ] value: 5
> 7
   "Answer the factorial of the receiver."

   self = 0 ifTrue: [ ^ 1 ].
   self > 0 ifTrue: [ ^ self * (self - 1) factorial ].
   self error: 'Not valid for negative integers'