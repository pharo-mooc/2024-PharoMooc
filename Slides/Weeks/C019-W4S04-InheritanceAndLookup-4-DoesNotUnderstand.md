{
  self coucou: #stef

Node >> welcome
  [ self sayHello ]
  on: MessageNotUnderstood
  do: [ Transcript show: 'Something went wrong with a message' ]