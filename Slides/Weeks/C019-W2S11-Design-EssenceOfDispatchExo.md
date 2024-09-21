{"title" : "Exercises for Essence of Dispatch","slidesid" : "W2S11"}# Three Questions1. Implement `not`1. Implement `|` \(or\) and `ifTrue:ifFalse:`1. What is the goal of these exercises?# Exercise 1: Implement notPropose an implementation of `not` in a world where:- You have: `true`, `false`- You only have objects and messages- How would you implement: `not`?```   false not
   -> true

   true not
   -> false```# Exercise 2: Implement | (or)Propose an implementation of `or` in a world where:- You have: `true`, `false`- You only have objects and messages- How would you implement: `not`?```   true | true -> true
   true | false -> true
   true | anything -> true

   false | true -> true
   false | false -> false
   false | anything -> anything```# Exercise 3: Why These Exercises?- You are never going to implement Booleans in your life- So why do we think these exercises are so important?%  Local Variables:%  compile-command: "cd ../.. && ./compile.sh --to=Beamer Slides/Week2/C019SD-W2S13-Design-EssenceOfDispatchExo.pillar"%  End: