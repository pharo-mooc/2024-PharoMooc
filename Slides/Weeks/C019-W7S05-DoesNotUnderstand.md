{
   instanceVariableNames: 'target'
   ^ aMessage sendTo: self target
	instanceVariableNames: 'subject invocationCount'
	classVariableNames: ''
	package: 'LoggingProxy'
	invocationCount := 0. 
	subject := self
	"will be swapped by become:"
	Transcript show: 'performing ', aMessage printString; cr.
	invocationCount := invocationCount + 1.
	^ aMessage sendTo: subject
   ^ receiver perform: selector withArguments: args
point := 1@2.
LoggingProxy new become: point.
self assert: point invocationCount = 0.
self assert: point x + point y = 3.
self assert: point + (3@4) = (4@6).
self assert: point invocationCount = 3.
   | messageName |
   messageName := aMessage selector asString.
   (self class instVarNames includes: messageName)
      ifTrue: [self class compile:
                  messageName , String cr , ' ^ ' , messageName.
         ^ aMessage sendTo: self].
   super doesNotUnderstand: aMessage