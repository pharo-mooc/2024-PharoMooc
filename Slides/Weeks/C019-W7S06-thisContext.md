{
   self deprecated: 'Use bar.' on: '31/12/2015' in: 'Pharo50'.
   self bar
	"Warn that the sending method has been deprecated"
	
	(Deprecation
		method: thisContext sender method
		explanation: anExplanationString
		on: date
		in: version) signal
  ...
  Halt if: #testSetInitialized
  ...
  "This is the typical message to use for inserting breakpoints during debugging.
  The argument can be one of the following:
    - a block: if the Block has one arg, the calling object is bound to that.
    - an expression
    - a selector: Halt if found in the call chain"

  condition isSymbol ifTrue: [ ^ self haltIfCallChainContains: condition ].
  condition isBlock ifTrue: [ ^ self haltIfBlockWithCallingObject: condition].
  condition ifTrue: [self signal].
  | cntxt |
  cntxt := thisContext.
  [ cntxt sender isNil ] whileFalse: [
    cntxt := cntxt sender. 
    (cntxt selector = aSelector) ifTrue: [ self signal ] ].