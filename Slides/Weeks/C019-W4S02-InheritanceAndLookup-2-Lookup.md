{"title" : "Inheritance and Lookup","slidesid" : "W4S02","subtitle" : "2: Lookup"}# Goal- Understanding  - message sending  - method lookup  - semantics of `self`# Inheritance- Inheritance of state is static- Inheritance of behavior is dynamic# Message Sending<!columns|width=100<!column|width=38**Sending** a **message** is a two-step process:1. **look up** the **method** matching the message1. execute this method on the **receiver**!><!column|width=62![](figures/InheritanceDiagram-sendingMessage.png width=100)!>!># Method Lookup<!columns|width=100<!column|width=38The lookup starts in the **class** of the **receiver** then:- if the method is defined in the class, it is returned- otherwise the search continues in the superclass!><!column|width=62![](figures/InheritanceDiagram-lookupTwoStages.png width=100)!>!># Some Lookup Cases<!columns|width=100<!column|width=47Sending the message `color` to `aColoredRectangle`!><!column|width=53![](figures/InheritanceDiagram-lookup-superclass.png width=95)!>!># Some Lookup Cases<!columns|width=100<!column|width=47Sending the message `area` to `aColoredRectangle`!><!column|width=53![](figures/InheritanceDiagram-lookup-superclass.png width=95)!>!># self Always Represents the Receiver![](figures/LookupWithSelfInSuperclassMethod.png width=71)```A new foo
> ...
B new foo
> ...```# self Always Represents the Receiver![](figures/LookupWithSelfInSuperclassMethod.png width=71)```A new foo
> 10
B new foo
> 50```# What is self/this?Take 5 min and write the definition of `self` \(`this` in Java\).- your definition should have two points:  - what does `self` represent?  - how is a method looked up when a message is sent to `self`?# self Always Represents the Receiver![](figures/LookupWithSelfInSuperclassMethod.png width=71)```A new bar
> ...
B new bar
> ...```# self Always Represents the Receiver![](figures/LookupWithSelfInSuperclassMethod.png width=71)```A new bar
> 10
B new bar
> 50```# self Always Represents the Receiver<!columns|width=100<!column|width=35![](figures/LookupWithSelfInSuperclassMethod.png width=110)```    B new bar
    > 50```!><!column|width=65Evaluation of `aB bar`1. `aB`'s class is `B`1. no method `bar` in `B`1. look up in `A` - `bar` is found1. method `bar` is executed1. `self` refers to the receiver `aB`1. `foo` is sent to `self`1. look up `foo` in the `aB`'s class: `B`1. `foo` is found there and executed!>!># self/this- `self` represents the receiver of the message- `self` in Pharo, `this` in Java- The method lookup starts in the class of the receiver# self Always Represents the Receiver<!columns|width=100<!column|width=60![](figures/LookupWithSelfInSuperclassMethodThreeClasses.png width=100)!><!column|width=40```    A new bar
    > ...
    B new bar
    > ...
    C new bar
    > ...```!>!># self Always Represents the Receiver<!columns|width=100<!column|width=60![](figures/LookupWithSelfInSuperclassMethodThreeClasses.png width=100)!><!column|width=40```    A new bar
    > 10
    B new bar
    > 10
    C new bar
    > 50```!>!># What You Should Know- `self` always represents the receiver- Sending a message is a two-step process:  1. Look up the method matching the message  1. Execute this method on the receiver- Method lookup maps a message to a method- Method lookup starts in the class of the receiver  - ...and goes up in the hierarchy%  Local Variables:%  compile-command: "cd ../.. && ./compile.sh --to='Beamer' Slides/Week4/C019-W4S02-InheritanceAndLookup-2-Lookup.pillar"%  End: