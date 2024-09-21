{
- list item
-- subitem

Any text here
   ^ DocumentItem allSubclasses
      sorted: [ :class1 :class2 | class1 priority < class2 priority ]

Parser >> parse: line
   self documentClasses
      detect: [ :subclass |
         (subclass canParse: line)
            ifTrue: [ ^ subclass newFromLine: line ] ]
3628800
   ^ arguments includesSubCommand: self commandName

EvaluateCommandLineHandler class >> commandName
   ^ 'eval'

CommandLineHandler class >> allHandlers
   ^ self allSubclasses
      reject: [ :handler| handler isAbstract ]

CommandLineHandler class >> handlersFor: arguments
   ^ self allHandlers
      select: [ :handlerClass |
         handlerClass isResponsibleFor: arguments ]