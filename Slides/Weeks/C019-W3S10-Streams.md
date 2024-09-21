{"title" : "Stream Overview","slidesid" : "W3S10"}# What You Will Learn- What streams are?- How to use them# Streams- Iterate over a sequence of elements  - e.g., collection, file, network- Current position separates past from future![](figures/a_bcdeStef.png width=100&label=fig:a_bcde)# API Overview- Creating  - `anObject readStream`  - `anObject writeStream`  - `Collection streamContents: [:stream | ... ]`  - `(Read/Write)Stream on: aCollection`- Reading elements  - `next`  - `upTo: anObject`  - `upToEnd`- Writing elements  - `nextPut: anElement`  - `nextPutAll: aCollection`# Reading Elements- `next`, `upTo: anObject`, `upToEnd````| stream |
stream := #($a $b $c $d $e $f) readStream.

stream next.
> $a

stream upTo: $d.
>  #($b $c)

stream position.
> 4

stream upToEnd
> #($e $f)```# Writing Elements- `nextPut:`, `nextPutAll:````stream := (Array new: 6) writeStream.

stream nextPut: 1.
stream contents.
> #(1)

stream nextPutAll: #(4 8 2 6 7).
stream contents.
> #(1 4 8 2 6 7)```# Writing to a File```stream := 'hello.txt' asFileReference writeStream.
stream nextPutAll: 'Hello Pharo!'.
stream close.```# Reading from a File```stream := 'hello.txt' asFileReference readStream.

stream next.
> $H

stream upToEnd.
> 'ello Pharo!'

stream close```# Creating Collections from a StreamWhen you want to create a collection by writing to a stream:```stream := OrderedCollection new writeStream.
stream nextPut: 1.
stream contents```is equivalent to```OrderedCollection
   streamContents: [:stream | stream nextPut: 1]```Both scripts return a collection with number 1 inside.# What You Should Know- A stream can read from and write to  - collections, files and network- A stream maintains a current position- A stream can help create collections%  Local Variables:%  compile-command: "cd ../.. && ./compile.sh --to=Beamer Slides/Week3/C019-W3S10-Streams.pillar"%  End: