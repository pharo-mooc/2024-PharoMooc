{
   instanceVariableNames: 'count'
   classVariableNames: ''
   package: 'Seaside-Examples-Misc'.

WACounter >> initialize
   super initialize.
   count := 0

WACounter >> increase
   count := count + 1

WACounter >> decrease
   count := count - 1
   html heading: count.
   html anchor
      callback: [ self increase ];
      with: '++'.
   html space.
   html anchor
      callback: [ self decrease ];
      with: '--'
   self haltIf: (count-1 < 0).
   count := count - 1
        ^ Array with: self
   html heading: count.
   html anchor
      callback: [ 
         count odd 
            ifTrue: [ self increase ]
            ifFalse: [ 
               self inform: 'Even number!'. 
               count := count + 2] 
      ];
      with: '++'.
   html space.
   html anchor
   	callback: [ self decrease ];
   	with: '--'
    html form: [
         html text: 'Username:'.
         html textInput
            callback: [ :value | username := value ].
         html submitButton
            callback: [ self inform: 'Hi ', username ];
            text: 'Say Hello'. ].