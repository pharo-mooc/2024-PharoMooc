{
> #(nil nil nil nil)
> #(nil nil)
> an OrderedCollection(7 7 3 13)
> a Set( 7 3 13)
> an OrderedCollection('a' 'a' 'a' 'a' 'a')
> 'hates'

#('Calvin' 'hates' 'Suzie') asOrderedCollection  at: 2
> 'hates'
> #('calvin' #(1 2 3))
s := Set new.
s add: Set new;
    add: 1;
    add: 2.
s asArray
> an Array(1 2 a Set())
     do: [ :each | Transcript show: each ; cr ]
> 3
    at: 1 put: 'Calvin';
    at: 2 put: 'hates';
    at: 3 put: 'Suzie';
	size)
> 3
> 3
> 'hates'
> SubscriptOutOfBounds Error
> #('Calvin' 'loves' 'Suzie')
> #(45 'milou' 1300 true #tintin)
> Array
> #(45 38 'milou' 8)
> #(45 38 'milou' 8)
ordCol := OrderedCollection new.
ordCol add: 'Reef'; add: 'Pharo'; addFirst: 'Pharo'.
ordCol
> an OrderedCollection('Pharo' 'Reef' 'Pharo')
ordCol add: 'Seaside'.
ordCol
> an OrderedCollection('Pharo' 'Reef' 'Pharo' 'Seaside')
> an OrderedCollection('Pharo' 'Reef' 'Pharo' 'Pharo')
> a Set('Pharo' 'Reef')

  asSet

  asArray
days := Dictionary new.
days
  at: #January put: 31;
  at: #February put: 28;
  at: #March put: 31.
days := Dictionary new.
days
  at: #January put: 31;
  at: #February put: 28;
  at: #March put: 31.
  #February -> 28.
  #March -> 31} asDictionary
> #January
> 31
days := Dictionary new.
days
    at: #January put: 31;
    at: #February put: 28;
    at: #March put: 31.
> 31

days at: #NoMonth
> KeyNotFound Error

days at: #NoMonth ifAbsent: [0]
> 0
  28
  31

   ^ self valuesDo: aBlock
  [ :k :v | Transcript show: k asString, ' has ',  v printString, ' days' ; cr ]
  February has 28 days
  March has 31 days