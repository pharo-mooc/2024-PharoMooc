{"title" : "Seaside: A Glance at MetaData and REST","slidesid" : "W4S10"}# Magritte: Taking Advantages of MetaData- Describe once- Generate many times- No more manually created forms- Seaside component automatic generation# Address![](figures/Address.png width=100)# Address Description![](figures/AddressDescription.png width=120)# Describe```Address >> descriptionStreet
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
        max: 9999```# Interpret```anAddress description do: [ :description |
   Transcript
       show: description label; show: ':'; tab;
       show: (description toString: (anAddress readUsing: description));
       cr ]``````Street:	Schutzenmattstrasse
PLZ:	3012
Place:	Bern
Canton:	Bern```# Generate Forms```self call: (anAddress asComponent addValidatedForm; yourself)```![](figures/AddressForms.png width=35)# Generate Automatic Reports![](figures/Seaside-Quuve2.jpg width=100)# Seaside-REST- Smooth and easy integration- Annotation of domain objects- Natural conversion# Filter Definition```WARestfulFilter subclass: #TBRestfulFilter
	instanceVariableNames: ''
	classVariableNames: ''
	package: 'TinyBlog-REST'``````TBApplicationRootComponent class >> initialize
	   "self initialize"
	   | app |
	   app := WAAdmin register: self asApplicationAt: 'TinyBlog'.
	   app
	      addLibrary: JQDeploymentLibrary;
	      addLibrary: JQUiDeploymentLibrary;
	      addLibrary: TBSDeploymentLibrary.
	   app addFilter: TBRestfulFilter new.```# Getting All Blogs![](figures/RESTlistAll.png width=100)# Getting All blogs```TBRestfulFilter >> listAll
  <get>
  <produces: 'text/json'>

  ^ String streamContents: [ :astream | 
  		TBBlog current allBlogPosts
			do: [ :each | each javascriptOn: stream ]
			separatedBy: [ stream << ',' ] ] ```# Finding a Blog![](figures/RestPost.png width=100)# Finding a Blog```TBRestfulFilter >> post: title
  <get>
  <path: 'post/{title}'>
  <produces: 'text/json'>
  | post |
  post := TBBlog current postWithTitle: title.
  post ifNil: [ ^ self notFound ]. 
  ^ String streamContents: [ :astream | 
         post javascriptOn: astream ]```# With Search```TBRestfulFilter >> search: title
   <get>
   <path: 'search?title={title}'>
   <produces: 'text/json'>
   | post |
   post := TBBlog current postWithTitle: title.
   post ifNil: [ ^ self notFound ]. 
   ^ String streamContents: [ :astream | 
		post javascriptOn: astream attributes: #(title category date text) ]``````http://localhost:8080/TinyBlog/search?title=Welcome%20in%20TinyBlog```# Conclusion- Seaside supports the other REST API \(Delete, Post, Get,...\)- Seaside coupled with Magritte offers a really powerful combination- REST is nicely integrated in Seaside-REST- Have a look at Teapot for another REST solution%  Local Variables:%  compile-command: "cd ../.. && ./compile.sh --to=Beamer Slides/Week4/C019-W4S10-Seaside-MagritteREST.pillar"%  End: