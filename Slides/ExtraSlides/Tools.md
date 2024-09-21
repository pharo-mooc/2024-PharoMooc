{
"title" : "Tools shaped our mind... not anymore",
"author" : "S. Ducasse",
"slidesid" : "Master Class"
}

# Tools

- Shape our mind...
- Get moldable tools so that you can adapt  tools the way you think!
- And not the inverse
- Build fast your own tools.

# Pharo has AMAZING tools

- Finder
- Customizable inspector
- Scriptable debugger

# How to find information?
- Librairie are Large
- You know what you want 
- You do not know how to express it

# Ask Finder example-based queries?
- Provide objects and results
- Get the messages that match

# What are the messages send to Character 0 that return true?
![ ](figures/Finder0.png width=100)

# 11 ??? 2 should give 5
![ ](figures/Finder1.png width=100)

# 11 ??? 2 should give 5.5
![ ](figures/Finder2.png width=100)

# Customized object interaction/presentations

# Inspecting Live a 3D object
![ ](figures/cuboid.png width=100)

# The views of a file reference
- A file reference is just an id in a file system
- Limited API
- Quite simple and dry object

# Looking at a  file reference
![ ](figures/fileref1.png width=130)

# Oh! a file browser in my inspector!
![ ](figures/fileref2.png width=130)
# But I have a file reference: a dull object
![ ](figures/fileref3.png width=130)

# Quite boring object
- The API is rather simple.
![ ](figures/fileref4.png width=130)

# We can see the png :)
![ ](figures/fileref5.png width=130)

# Looking inside that PNG file
- May be we want to look inside
![ ](figures/fileref6.png width=130)

# But still a file reference!
![ ](figures/fileref7.png width=130)

# See! An Archive '.zip'
![ ](figures/fileref8.png width=130)Would be nice to see what is inside...

# Kind of clear…
![ ](figures/fileref9.png width=130)

# An object can expose multiple interactive views!
- You can use the best view for your task!
- You can add views to your domain objects
![ ](figures/fileref10.png width=130)

# It is supra cool but it is not magic

# Implement a pane!
![ ](figures/fileref11.png width=110)

# More?
<!columns|width=100

<!column|width=40

- Files are boring?
- What about inside the system?

!>

<!column|width=70

![ ](figures/voyageaucentre.jpg width=100)
!>


!>

# A class is an object we can inspect
![ ](figures/comp1.png width=130)
# “A class has a method dictionary” they said… let us verify
![ ](figures/comp2.png width=120)
# Dissecting one method object
![ ](figures/comp3-0.png width=120)
# I do not want to be a compiler!
![ ](figures/comp3-1.png width=120)
# It looks like a method
![ ](figures/comp4.png width=120)
# Numbers are not that obscure
![ ](figures/comp5.png width=120)
# And mapping them to the good abstraction helps
![ ](figures/comp6.png width=120)
# Yes pushRcvr: 1 means the second field!
![ ](figures/comp7.png width=120)
# Pharo pro devs
- Get productivity boost
- Xtreme TDD 
  - write test, 
  - test fails and 
  - code in debugger

# Hot update on the fly customizable debugger
- Hot code update
- Recompile on the fly
- Smart breakpoints \(Pharo 90\)
- Scripting \(Pharo 90\)
- Plugins

# Default
![ ](figures/debugger1.png width=130)
# With plugins
![ ](figures/debugger2.png width=130)
# Domain specific
![ ](figures/debugger3.png width=130)
# Visualisations
The next level
- Scripting your own interactive visualisations 
- Roassal by A. Bergel at University of Chile at Santiaho
- Simply gorgeous Excellent
- check http://agilevisualisation.com

# A simple script
<!columns|width=100

<!column|width=70


```
b := RTMondrian new.
b shape rectangle
	withBorder;
	width: [ :cls | cls numberOfVariables * 5 ];
	height: [ :cls | cls numberOfMethods ].

b nodes: Collection withAllSubclasses.
b edges connectToAll: [ :cls | cls subclasses ].
b layout tree.
b normalizer
	normalizeColorAsGray: [ :cls | 
cls numberOfLinesOfCode ].
b
```

!>

<!column|width=50

![ ](figures/roassalsimple.png width=150)
!>


!>

# Execution of IA generating tests
![ ](figures/roassaltestGen.png width=90)
# Javascript analysis
![ ](figures/roassalHunter.png width=120)
# Android execution
![ ](figures/roassalAndroid.png width=90)
# HTTP traffic analysis by beta9
[http://youtu.be/rIBbeMdFCys](http://youtu.be/rIBbeMdFCys)![ ](figures/SvenLog.png width=100)
# Probabilistic data structure by oscoco
<!columns|width=100

<!column|width=40

- [https://github.com/osoco/PharoPDS](https://github.com/osoco/PharoPDS)
- Defined new data structures
- And the analysis tools

!>

<!column|width=60

![ ](figures/tools-Datastructure.png width=160)
!>


!>

# Empowering is the right word
- Moldable tools are powerful
- Productivity boost
- Tried to give you my feeling
But “The idea of experience does not replace experience.” Alain
# An important meta question
**How to invent new things with the same tools than any body else?**