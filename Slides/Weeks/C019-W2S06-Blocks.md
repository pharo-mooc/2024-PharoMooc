{
-> Error
> [ 1 /0 ]
1 + 2 
> 3
> 8
> Error
> 7
  x + 33.
  x + 2 ] value: 5
> 7
add2 := [ :x | x + 2 ].

add2 value: 5.
> 7

add2 value: 33
> 35
> 12
> 12
  self do: [ :index | | args |
    args := ....
    aBoolean
      ifTrue: [ anObject do: args ]
      ifFalse: [ anObject doDifferently: args ] ].
  "Answer the factorial of the receiver."
  
  self = 0 ifTrue: [ ^ 1 ].
  self > 0 ifTrue: [ ^ self * (self - 1) factorial ].
  self error: 'Not valid for negative integers'
>1

42 factorial
>1405006117752879898543142606244511569936384000000000
  | tmp |
  expression1.
  ... variable1 ...
] value: ... value: ...