{
   self assert: Color white convert equals: '#FFFFFF'.
   self assert: Color red convert equals: '#FF0000'.
   self assert: Color black convert equals: '#000000'
   | table aColorString |
   table := #('0' '1' '2' '3' '4' '5' '6' '7' '8' '9' 'A' 'B' 'C' 'D' 'E' 'F').

   table do: [ :each |
      aColorString := '#', each, each, '0000'.
      self assert: (Color fromString: aColorString) convert equals: aColorString ].
   self assert: (2r11 bitShift: 2) equals: 2r1100.
   self assert: (2r1011 bitShift: -2) equals: 2r10.
   "Shift 1 bit left then right and test for 1"
   
   1 to: 100 do: [:i | 
      self 
        assert: ((1 bitShift: i) bitShift: i negated) 
        equals: 1].
   | s |
   s := '#000000' copy.
   s at: 2 put: (Character digitValue: ((rgb bitShift: -6 - RedShift) bitAnd: 15)).
   s at: 3 put: (Character digitValue: ((rgb bitShift: -2 - RedShift) bitAnd: 15)).
   s at: 4 put: (Character digitValue: ((rgb bitShift: -6 - GreenShift) bitAnd: 15)).
   s at: 5 put: (Character digitValue: ((rgb bitShift: -2 - GreenShift) bitAnd: 15)).
   s at: 6 put: (Character digitValue: ((rgb bitShift: -6 - BlueShift) bitAnd: 15)).
   s at: 7 put: (Character digitValue: ((rgb bitShift: -2 - BlueShift) bitAnd: 15)).
   ^ s
	| table aColorString |
	self assert: Color white asHexString equals: 'FFFFFF'.
	self assert: Color red asHexString equals: 'FF0000'.
	self assert: Color black asHexString equals: '000000'.