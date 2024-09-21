{
  url: 'http://localhost:8181/books/1';
  get
  url: 'http://localhost:8181/books/1';
  formAt: 'author' put: 'van Caekenberghe et al';
  formAt: 'title'  put: 'Entreprise Pharo';
  post
teapot := Teapot configure: { 
    #defaultOutput -> #json. #port -> 8181 }.
teapot
 GET: '/' -> '<h1>A simple book server</h1>'; output: #html;
 GET: '/books' -> books;
 GET: '/books/<id:IsInteger>' 
   -> [ :request | books at: (request at: #id) asString];
 POST: '/books/<id>' 
   -> [ :request | | book |
          book := { 'author' -> (request at: #author). 
          'title'  -> (request at: #title) } asDictionary.
          books at: (request at: #id) put: book ];   
 start.
  books := Dictionary new.
  teapot := Teapot configure: {  #defaultOutput -> #json.   #port -> 8181 . #debugMode -> true }.
 GET: '/' 
   -> '<h1>A simple book server</h1>'; output: #html;
 GET: '/books' 
   -> books;
 GET: '/books/<id:IsInteger>' 
   -> [ :request | books at: (request at: #id) asString];
 POST: '/books/<id>' 
   -> [ :request | | book |
      book := { 'author' -> (request at: #author) . 
        'title' -> (request at: #title) } asDictionary.
      books at: (request at: #id) put: book ];   
 start.
 GET: '/books/<id:IsInteger>'
   -> [ :request | books at: (request at: #id) asString];