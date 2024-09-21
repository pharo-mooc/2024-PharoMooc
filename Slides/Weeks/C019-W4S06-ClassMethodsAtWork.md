{"title" : "Class Methods At Work","slidesid" : "W4S06"}# What You Will Learn- Class methods are normal methods- Most class methods create new instances  - but they can be used for other things# Parsing LinesImagine we want to parse```!Section Title
- list item
-- subitem

Any text here```# A Possible Design![](figures/items.png width=80)- Document item **classes** know  - if they can parse a line \(`canParse:`\)  - how to create instances \(`newFromLine:`\)# Parsing Lines![](figures/items.png width=60)```Parser >> documentClasses
   ^ DocumentItem allSubclasses
      sorted: [ :class1 :class2 | class1 priority < class2 priority ]

Parser >> parse: line
   self documentClasses
      detect: [ :subclass |
         (subclass canParse: line)
            ifTrue: [ ^ subclass newFromLine: line ] ]```# The Command-Line Handler- the Pharo command-line interface \(CLI\) uses the same approach- each subclass of `CommandLineHandler` knows how to deal with one command- the correct subclass is selected by sending messages to the class```language=bash$ pharo Pharo.image eval "10 factorial"
3628800```# The Command-Line Handler```CommandLineHandler class >> isResponsibleFor: arguments
   ^ arguments includesSubCommand: self commandName

EvaluateCommandLineHandler class >> commandName
   ^ 'eval'

CommandLineHandler class >> allHandlers
   ^ self allSubclasses
      reject: [ :handler| handler isAbstract ]

CommandLineHandler class >> handlersFor: arguments
   ^ self allHandlers
      select: [ :handlerClass |
         handlerClass isResponsibleFor: arguments ]```# Conclusion- Classes are objects and can be sent messages- Method lookup is exactly the same as for all objects:  - go to the class of the receiver  - follow inheritance chain- More during the lecture _Understanding Metaclasses_- Pharo makes it easy to iterate over subclasses%  Local Variables:%  compile-command: "cd ../.. && ./compile.sh --to=Beamer Slides/Week4/C019-W4S06-ClassMethodsAtWork.pillar"%  End: