{
    instanceVariableNames: 'counters'
    classVariableNames: ''
    package: 'Seaside-Examples-Misc'.
	
WAMultiCounter >> initialize
    super initialize.
    counters := (1 to: 5) collect: [ :each | WACounter new ].

WAMultiCounter >> children
    ^ counters
		
WAMultiCounter >> renderContentOn: html
    counters do: [ :each | html render: each ]
    instanceVariableNames: 'children'
    classVariableNames: ''
    package: 'Seaside-Examples-Misc'.

MyApp >> initialize
    super initialize.
    children := { Greeter new. 
		 WATwitterCounter new. WACounter new }.

MyApp >> children
    ^ children

MyApp >> renderContentOn: html
    children do: [ :each | html render: each ]
        separatedBy: [ html line ]
   "..."
   selectedChild := children first

MyApp >> renderContentOn: html
   self renderMenuOn: html.
   html render: selectedChild

MyApp >> renderMenuOn: html
   html unorderedList: [
      self children do: [ :child |
         html listItem: [
            html anchor
               class: 'active' if: child = selectedChild;
               callback: [ selectedChild := child ];
               with: child className ]]]
    "..."
    html tbsButton beDefault; 
        callback: [ self setCountToUserValue ]; with: 'Set Value'
    "..."

WATwitterCounter >> setCountToUserValue
    | webDialog newCounterValueByUser |
    webDialog := WAInputDialog new
        addMessage: 'Enter a new value for the counter:';
        default: '0';
        label: 'Ok';
        yourself.
    newCounterValueByUser := self call: webDialog.
    count := newCounterValueByUser asNumber
	html form
		defaultAction: [ self answer: value ];
		with: [
			html div: [
				html textInput on: #value of: self.
				html space.
				html submitButton
					callback: [ self answer: value ];
					text: self label ] ]
    instanceVariableNames: ''
    classVariableNames: ''
    package: 'SeaExample'
    | value1 value2 |
    value1 := self request: 'first number'.
    value2 := self request: 'second number'.
    self inform: value1 asNumber + value2 asNumber
	"Display an input dialog with the question aRequestString, the button label aLabelString and the default string aDefaultString. Passes the answer into aBlock."
	
    self 
         call: (WAInputDialog new
            addMessage: aRequestString;
            default: aDefaultString;
            label: aLabelString;
            yourself)
        onAnswer: aBlock	
    "Display a dialog with aString to the user until he clicks the ok button. Continue by evaluating aBlock."

    self 
        call: (WAFormDialog new
            addMessage: aString;
            yourself)
        onAnswer: aBlock