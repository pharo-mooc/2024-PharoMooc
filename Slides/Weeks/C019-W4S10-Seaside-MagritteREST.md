{
   ^ MAStringDescription new
        autoAccessor: #street;
        label: 'Street';
        priority: 100

Address >> descriptionPlz
   ^ MANumberDescription new
        autoAccessor: #plz;
        priority: 200; label: 'PLZ';
        beRequired;
        min: 1000; 
        max: 9999
   Transcript
       show: description label; show: ':'; tab;
       show: (description toString: (anAddress readUsing: description));
       cr ]
PLZ:	3012
Place:	Bern
Canton:	Bern
	instanceVariableNames: ''
	classVariableNames: ''
	package: 'TinyBlog-REST'
	   "self initialize"
	   | app |
	   app := WAAdmin register: self asApplicationAt: 'TinyBlog'.
	   app
	      addLibrary: JQDeploymentLibrary;
	      addLibrary: JQUiDeploymentLibrary;
	      addLibrary: TBSDeploymentLibrary.
	   app addFilter: TBRestfulFilter new.
  <get>
  <produces: 'text/json'>

  ^ String streamContents: [ :astream | 
  		TBBlog current allBlogPosts
			do: [ :each | each javascriptOn: stream ]
			separatedBy: [ stream << ',' ] ] 
  <get>
  <path: 'post/{title}'>
  <produces: 'text/json'>
  | post |
  post := TBBlog current postWithTitle: title.
  post ifNil: [ ^ self notFound ]. 
  ^ String streamContents: [ :astream | 
         post javascriptOn: astream ]
   <get>
   <path: 'search?title={title}'>
   <produces: 'text/json'>
   | post |
   post := TBBlog current postWithTitle: title.
   post ifNil: [ ^ self notFound ]. 
   ^ String streamContents: [ :astream | 
		post javascriptOn: astream attributes: #(title category date text) ]