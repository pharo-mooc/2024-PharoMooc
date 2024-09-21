{
coll := #(1 2 3 4 5 6 7 8 9 10) asOrderedCollection.
[ 1000000 timesRepeat: [ 
		(coll select: [ :each | each > 5]) collect: [ :i | i * i ]]
	] timeToRun
>  "0:00:00:00.517"
coll := #(1 2 3 4 5 6 7 8 9 10) asOrderedCollection.
[ 1000000 timesRepeat: [ 
		coll 
			select: [ :each | each > 5]
			thenCollect: [ :i | i * i ]]
		] timeToRun 
> "0:00:00:00.362"
> '610.234 per second' 
  spyOn: [ 20 timesRepeat: [ 
            Transcript show: 1000 factorial printString ] ]