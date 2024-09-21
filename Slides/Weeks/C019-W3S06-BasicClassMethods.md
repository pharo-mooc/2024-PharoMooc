{"title" : "Class Methods","slidesid" : "W3S06"}# Class Methods1. in Pharo, everything is an object1. objects can receive messages1. classes are objects tooClasses can receive messages# Examples```Time now
> 9:18:36.304688 pm```The message `now` is sent to the class `Time````Date today
> 29 July 2015```The message `today` is sent to the class `Date`# Examples```FileLocator workingDirectory``````ZnEasy getPng: 'http://pharo.org/web/files/pharo.png'``````ZnServer startDefaultOn: 8080```# Class Methods are Defined on Class SideNote the `Class` button pressed!![](figures/ClassMethodDateToday.png width=90)# Common Mistake```Counter class >> withValue: anInteger
   self new
      value: anInteger;
      yourself````Counter withValue: 10` returns the class `Counter` instead of a new instance# Why?```Counter class >> withValue: anInteger
   self new
      value: anInteger;
      yourself```is equivalent to```Counter class >> withValue: anInteger
   self new
      value: anInteger;
      yourself.
   ^ self````self` here is the class `Counter` \(the receiver of the message\)# Solution```Counter class >> withValue: anInteger
   ^ self new
      value: anInteger;
      yourself```# Summary- Classes are objects- Messages can be sent to classes too- Class-side methods are no different from other methods- Most class-side methods create new instances- To define a class-side method, press the `class` button%  Local Variables:%  compile-command: "cd ../.. && ./compile.sh --to=Beamer Slides/Week3/C019-W3S06-BasicClassMethods.pillar"%  End: