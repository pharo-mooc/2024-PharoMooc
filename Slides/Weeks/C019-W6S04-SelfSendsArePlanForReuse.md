{
   | defaultNodeSize |
   defaultNodeSize := mainCoordinate / maximizeViewRatio.
   self window add:
      (UINode new
         with: bandWidth * 55 / defaultWindowSize).
   previousNodeSize := defaultNodeSize.
   ...
  | defaultNodeSize |
  defaultNodeSize :=
     (mainCoordinate / maximizeViewRatio) + 10.
  self window add:
      (UINode new
         with: bandWidth * 55 / defaultWindowSize).
  previousNodeSize := defaultNodeSize.
  | defaultNodeSize |
  defaultNodeSize := (mainCoordinate / maximizeViewRatio).
  self window add:
      (UINode new
         with: bandWidth * 55 / defaultWindowSize).
  previousNodeSize := defaultNodeSize.
   | defaultNodeSize |
   defaultNodeSize := self ratio.
   self window add:
      (UINode new
         with: bandWidth * 55 / defaultWindowSize).
   previousNodeSize := defaultNodeSize.

Node >> ratio
   ^ mainCoordinate / maximizeViewRatio
   ^ mainCoordinate / maximizeViewRatio
   ^ super ratio + 10
   | defaultNodeSize |
   defaultNodeSize := self ratio.
   self window add:
      (UINode new
         with: bandWidth * 55 / defaultWindowSize).
   previousNodeSize := defaultNodeSize.
   | defaultNodeSize |
   defaultNodeSize := self ratio.
   self window add: self uiNode.
   previousNodeSize := defaultNodeSize.
   ^ UINode new
      with: bandWidth * 55 / defaultWindowSize
   ^ UINode new
      with: bandWidth * 55 / defaultWindowSize
   ^ self uiNodeClass new
      with: bandWidth * 55 / defaultWindowSize.
   ^ UINode
   ^ self uiNodeClass new
      with: bandWidth * 55 / defaultWindowSize.
   ^ self uiNodeClass new
      with: bandWidth * self averageRatio / defaultWindowSize.

Node >> averageRatio
   ^ 55
   ^ averageRatio ifNil: [ self defaultAverageRatio ]
Node >> defaultAverageRatio
   ^ 55
Node >> averageRatio: aNumber
   averageRatio := aNumber