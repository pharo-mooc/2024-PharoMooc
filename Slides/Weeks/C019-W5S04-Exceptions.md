{
  x := 7.
  y := 0.
  [ x / y ]
      on: ZeroDivide
      do: [ :exception | Transcript show: exception description; cr.
           0 ]
   > 0
  (Warning new messageText: 'Pay attention') signal
  Warning signal: 'description of the exception'

  self assert: (Date nameOfMonth: 1) equals: #January.

  self
    shouldnt: [ Date nameOfMonth: 2 ]
    raise: SubscriptOutOfBounds.
  self
    should: [ Date nameOfMonth: 13 ]
    raise: SubscriptOutOfBounds.

  ^ MessageNotUnderstood new
       message: aMessage;
       receiver: self;
       signal
  "Add a title line at the top of this menu."
  self deprecated: 'Use method addTitle: instead' on: '29 september' in: #Pharo40.
  self addTitle: aString
  "Warn that the sending method has been deprecated"
  (Deprecation
      method: thisContext sender method
      explanation: anExplanationString
      on: date
      in: version) signal
      on: ZeroDivide, Warning
      do: [ :ex | what you want ]
  exceptionSet := ExceptionSet with: ZeroDivide with: Warning.
  [do some work]
      on: exceptionSet
      do: [ :ex | what you want ]
  "Profile system activity during execution of aBlock."
  self startProfiling.
  aBlock ensure: [ self stopProfiling ]
  "Schedule this Delay, then wait on its semaphore. The current process will be suspended for the amount of time specified when this Delay was created."

  self schedule.
  [ delaySemaphore wait ] ifCurtailed: [ self unschedule ]
  on: Notification
  do: [ :ex |ex return: 'Value from handler' ]

  >  'Value from handler'
		on: Notification
		do: [ :ex | ex resume: 'Value from handler' ]

> 'Value from protected block'.