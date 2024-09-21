{
  "This method illustrates the complete syntax."
  <aMethodAnnotation>

  | y |
  true & false not & (nil isNil)
    ifFalse: [ self halt ].
  y := self size + super size.
  #($a #a 'a' 1 1.0)
    do: [ :each | Transcript
            show: (each class name);
            show: (each printString);
            show: ' ' ].
  ^ x < y
   asMorph openInWindow
> 7 
 url: 'https://en.wikipedia.org/w/index.php';
 queryAt: 'title' put: 'Pharo';
 queryAt: 'action'  put: 'edit';
 get
   "Answer the factorial of the receiver."
   self = 0 ifTrue: [ ^ 1 ].
   self > 0 ifTrue: [ ^ self * (self - 1) factorial ].
   self error: 'Not valid for negative integers'
> 1
> 2
> 3
> 4
  do: [ :each | Transcript show: each abs printString ; cr ]
> 1
> 2
> 4
> 86
  do: [ :each | Transcript show: each abs printString ; cr ]
> 1
> 2
> 4
> 86
   "comment stating purpose of message"

  | temporary variable names |
  statements