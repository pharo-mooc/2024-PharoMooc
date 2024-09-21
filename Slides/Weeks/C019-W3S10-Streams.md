{
stream := #($a $b $c $d $e $f) readStream.

stream next.
> $a

stream upTo: $d.
>  #($b $c)

stream position.
> 4

stream upToEnd
> #($e $f)

stream nextPut: 1.
stream contents.
> #(1)

stream nextPutAll: #(4 8 2 6 7).
stream contents.
> #(1 4 8 2 6 7)
stream nextPutAll: 'Hello Pharo!'.
stream close.

stream next.
> $H

stream upToEnd.
> 'ello Pharo!'

stream close
stream nextPut: 1.
stream contents
   streamContents: [:stream | stream nextPut: 1]