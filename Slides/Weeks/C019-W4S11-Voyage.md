{
repository := VOMongoRepository
    host: 'localhost'
    database: 'demo'.
repository enableSingleton.
repository := VOMemoryRepository new.
repository enableSingleton.
	instanceVariableNames: 'name level powers'
	classVariableNames: ''
	package: 'SuperHeroes'

Hero >> name
    ^ name
Hero >> name: aString    
    name := aString
Hero >> level
    ^ level
Hero >> level: anObject    
    level := anObject
Hero >> powers
    ^ powers ifNil: [ powers := Set new ]
Hero >> addPower: aPower
    self powers add: aPower
	instanceVariableNames: 'name'
	classVariableNames: ''
	package: 'SuperHeroes'.

Power>>name
    ^ name
Power>>name: aString    
    name := aString
    ^ true
    name: 'Spiderman';
    level: #epic;
    addPower: (Power new name: 'Super-strength');
    addPower: (Power new name: 'Wall-climbing');
    addPower: (Power new name: 'Spider instinct');
    save.

Hero new 
    name: 'Wolverine';
    level: #epic;
    addPower: (Power new name: 'Regeneration');
    addPower: (Power new name: 'Adamantium claws');
    save.
{
	"_id" : ObjectId("d847065c56d0ad09b4000001"),
	"#version" : 688076276,
	"#instanceOf" : "Hero",
	"level" : "epic",
	"name" : "Spiderman",
	"powers" : [
		{
			"#instanceOf" : "Power",
			"name" : "Spider instinct"
		},
		{
			"#instanceOf" : "Power",
			"name" : "Super-strength"
		},
		{
			"#instanceOf" : "Power",
			"name" : "Wall-climbing"
		}
	]
}
> an OrderedCollection(a Hero, a Hero)
> a Hero
> an OrderedCollection(a Hero, a Hero)
> a Hero
> an OrderedCollection(a Hero, a Hero)
    selectMany: { #level -> #epic } asDictionary
    sortBy: { #name -> VOOrder ascending }
    limit: 10
    offset: 0. 
> an OrderedCollection(a Hero, a Hero)
> 2
> 1.
> Hero class
hero remove.
> a Hero
  ^ true
Power new name: 'Super-strength'; save.
superStrength := Power selectOne: [ :each | each name = 'Super-strength']. 
Hero new 
    name: 'Superman';
    level: #epic;
    addPower: fly;
    addPower: superStrength;
    save.
{
	"_id" : ObjectId("d8474983421aa909b4000008"),
	"#version" : NumberLong("3874503784"),
	"#instanceOf" : "Hero",
	"level" : "epic",
	"name" : "Superman",
	"powers" : [
		{
			"#collection" : "Power",
			"#instanceOf" : "Power",
			"__id" : ObjectId("d84745dd421aa909b4000005")
		},
		{
			"#collection" : "Power",
			"#instanceOf" : "Power",
			"__id" : ObjectId("d84745dd421aa909b4000006")
		}
	]
}