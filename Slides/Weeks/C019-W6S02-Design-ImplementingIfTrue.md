{
    ifTrue: [ self takeMyUmbrella ]
    ifFalse: [ self takeMySunglasses ]
   -> 5

   true ifTrue: [ 3 ] ifFalse: [ 5 ]
   -> 3
   ^ aTrueBlock value
   ^ aFalseBlock value