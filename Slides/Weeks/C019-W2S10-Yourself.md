{
> 2
   "Include newObject as one of the receiver's elements, but only if not already present. Answer newObject."
   [...]
   ^ newObject
> 2
   s := Set new.
   s add: 2.
   s
   ^ self
   add: 2;
   yourself
> aSet
   "Answer an instance of me containing anObject."
   | instance |
   instance := self new.
   instance add: anObject.
   ^ instance
   "Answer an instance of me containing anObject."
   ^ self new
      add: anObject;
      yourself