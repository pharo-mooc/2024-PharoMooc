{
   -> true

   true not
   -> false
   "Negation -- answer true since the receiver is false."
   ^ true
   "Negation -- answer false since the receiver is true."
   ^ false
   "Abstract method. Negation: Answer true if the receiver is false, answer false if the receiver is true."
   self subclassResponsibility
true | false -> true
true | anything -> true
false | false -> false
false | anything -> anything
   "Abstract method. Evaluating Or: Evaluate the argument.
   Answer true if either the receiver or the argument is true."
   self subclassResponsibility
false | false -> false
false | anything -> anything
   "Evaluating Or -- answer with the argument, aBoolean."
   ^ aBoolean
true | false -> true
true | anything -> true
   "Evaluating Or -- answer true since the receiver is true."
   ^ true
   "Evaluating disjunction (Or) -- answer true since the receiver is true."
   ^ true
   "Evaluating disjunction (Or) -- answer true since the receiver is true."
   ^ self