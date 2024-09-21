{"title" : "DieHandle new vs. self class new","slidesid" : "W6S03"}# From the ExerciseTo support ```(DieHandle new add: (Die faces: 4); yourself) 
	+ (DieHandle new add: (Die faces: 6); yourself)```We defined `+` as ```DieHandle >> + aDieHandle
  | handle |
  handle := DieHandle new.
  self dice do: [ :each | handle addDie: each ]. 
  aDieHandle dice do: [ :each | handle addDie: each ]. 
  ^ handle```# What Is The Difference...Between ```DieHandle >> + aDieHandle
  | handle |
  handle := DieHandle new.```And ```DieHandle >> + aDieHandle
  | handle |
  handle := self class new.```Let us see....# What If We Create A New Subclass```DieHandle subclass: MemoDieHandle
  ....``````(MemoDieHandle new add: (Die faces: 4); yourself) 
   + (MemoDieHandle new add: (Die faces: 6); yourself)
> aDieHandle```We get a `DieHandle` instance back and not a `MemoDieHandle` instance!!!# Solution 1: Creating a Hook```DieHandle >> + aDieHandle
  | handle |
  handle := self handleClass new.
  self dice do: [ :each | handle addDie: each ]. 
  aDieHandle dice do: [ :each | handle addDie: each ]. 
  ^ handle``````DieHandle >> handleClass
  ^ DieHandle```A subclass may redefine `handleClass` ```MemoDieHandle >> handleClass
  ^ MemoDieHandle```# Solution 1: Creating a Hook```(MemoDieHandle new add: (Die faces: 4); yourself) 
   + (MemoDieHandle new add: (Die faces: 6); yourself)
> aMemoDieHandle```We get an instance of the subclass!# But We Can Do Better!Let us see- In each subclass we should redefine the hook method  `handleClass`- This is tedious# Solution 2```DieHandle >> + aDieHandle
  | handle |
  handle := self class new.
  self dice do: [ :each | handle addDie: each ]. 
  aDieHandle dice do: [ :each | handle addDie: each ]. 
  ^ handle```- `self class` always returns the class of the receiver- We get instances of the same kind of the receiver # ConclusionIf we define a subclass of `DieHandle`, and send the message `+` to an instance- With `DieHandle new`, `+` does not return an instance of the subclass but of `DieHandle`- With `self class new`, `+` returns an instance of the receiver: an instance of a potential subclass