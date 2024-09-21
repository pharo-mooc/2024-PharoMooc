{
   animal isDog
      ifTrue: [ animal shakeTail ].
   animal isDuck
      ifTrue: [ animal quack ].
   animal isCat ifTrue: [ ... ].
   self shakeTail
Duck >> showHappiness
   self quack
Cat >> showHappiness
   ...
   self noRule ifTrue: [ ^ nil ]
   ^ self rulesAppliedTo: aFact
   ifNotNil: [ :rules |
      rules do: [ :each | ... ]
   self noRule ifTrue: [ ^ #() ]
   ^ self rulesAppliedTo: aFact
   do: [:each | ... ]
   canWrite ifFalse: [ self cantWriteError ].
   ...
FileStream >> cantWriteError
   (CantWriteError file: file) signal
   super initialize.
   members := OrderedCollection new
   ^ cachedDescent ifNil: [
        cachedDescent := (self face descender * self pixelSize //
                               self face unitsPerEm) negated ]
   self selectedTool
      ifNotNil: [ :tool | tool attachHandles ]

ToolPalette >> previousAction
   self selectedTool
      ifNotNil: [ :tool | tool detachHandles ]
   ^ self
NoTool >> detachHandles
   ^ self
   self selectedTool: NoTool new
ToolPalette >> nextAction
   self selectedTool attachHandles
ToolPalette >> previousAction
   self selectedTool detachHandles