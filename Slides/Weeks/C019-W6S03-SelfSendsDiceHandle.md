{
	+ (DieHandle new add: (Die faces: 6); yourself)
  | handle |
  handle := DieHandle new.
  self dice do: [ :each | handle addDie: each ]. 
  aDieHandle dice do: [ :each | handle addDie: each ]. 
  ^ handle
  | handle |
  handle := DieHandle new.
  | handle |
  handle := self class new.
  ....
   + (MemoDieHandle new add: (Die faces: 6); yourself)
> aDieHandle
  | handle |
  handle := self handleClass new.
  self dice do: [ :each | handle addDie: each ]. 
  aDieHandle dice do: [ :each | handle addDie: each ]. 
  ^ handle
  ^ DieHandle
  ^ MemoDieHandle
   + (MemoDieHandle new add: (Die faces: 6); yourself)
> aMemoDieHandle
  | handle |
  handle := self class new.
  self dice do: [ :each | handle addDie: each ]. 
  aDieHandle dice do: [ :each | handle addDie: each ]. 
  ^ handle