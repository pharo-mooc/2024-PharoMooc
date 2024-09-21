{
for(Person person: persons)
    strings.add(person.name());
  > #(2 3 4 35 4)
aCol :=  #(16 11 68 19).
result := aCol species new: aCol size.
1 to: aCollection size do:
    [ :each | result at: each put: (aCol at: each) odd ].
^ result
  > #(11 19)
> #(16 68)
> 11
> 0
    with:  #(10 20 30)
    do: [ :x :y | Transcript show: (y * x) ; cr ]
    #('a' 'b' 'c')
        do: [ :each | s << each ]
        separatedBy: [ s << ', ' ]
]
> 'a, b, c'
> a OrderedDictionary(false->#(1 3 5 7) true->#(2 4 6) )
> #(#(1 2) #(3) #(4) #(5 6)))
> #(1 2 3 4 5 6 )
  "Evaluate aBlock with each of the receiver's elements as the argument."

  1 to: self size do: [:i | aBlock value: (self at: i)]