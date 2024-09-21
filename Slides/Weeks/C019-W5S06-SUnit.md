{
    ...
  | empty |
  empty := Set new.   "Context"
  empty add: 5.   "Stimulus"
  empty add: 5.
  self assert: empty size = 1.   "Check"

SetTestCase run: #testAdd
  "this demonstrates that adjacent runs with equal attributes are merged. "
  | runArray |
  runArray := RunArray new.
  runArray
    addLast: TextEmphasis normal times: 5;
    addLast: TextEmphasis bold times: 5;
    addLast: TextEmphasis bold times: 5.
  self assert: runArray runs size equals: 2.
  self
    should: [ Set new remove: 1 ]
    raise: NotFound
  self
    shouldnt: [ Set new add: 1 ]
    raise: NotFound
  | empty |
  empty := Set new.
  self
    assert: (empty occurrencesOf: 0)
    equals: 0.
  empty add: 5; add: 5.
  self
    assert: (empty occurrencesOf: 5)
    equals: 1
  empty := Set new
  self
    assert: (empty occurrencesOf: 0)
    equals: 0.
  empty add: 5; add: 5.
  self
    assert: (empty occurrencesOf: 5)
    equals: 1