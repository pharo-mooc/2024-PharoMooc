{
   Halt now.
  Halt once.
  ...
  Halt if: #printString
  ...
  Halt if: #testLargeDie
   (Time current
      between: minTime asTime
      and: maxTime asTime)
         ifTrue: [ self signal ]

Die >> faces
   ...
   Halt between: '00:00' and: '02:00'