{"title" : "Hooks","slidesid" : "Inria Academy","author" : "S. Ducasse"}# Analysing...```IconStyler >> addIconStyle: aNode from: start to: stop color: aColor
	| conf |
	(self shouldStyleNode: aNode) ifFalse: [ ^self ].
	conf := RubConfigurationChange new.
		conf configurationBlock: [ :text| |r| 
			r := RubTextSegmentMorph from: start to: stop + 1.
			text addSegment: r.
			r label: (self iconLabelBlock: aNode).
			r icon: (self iconFor: aNode).
			r iconBlock: (self iconBlock: aNode).
			r color: aColor.
			r borderColor: self borderColor.
		].
		textModel announce: conf```# Crying for a hook```ErrorNodeStyler >> addIconStyle: aNode from: start to: stop color: aColor
	| conf |
	(self shouldStyleNode: aNode) ifFalse: [ ^self ].
	conf := RubConfigurationChange new.
	conf configurationBlock: [ :text| |r| 
		r := RubUnderlinedSegmentMorph from: aNode start to: aNode stop + 1.
		text addSegment: r.
		r label: (self iconLabelBlock: aNode).
		r icon: (self iconFor: aNode).
		r iconBlock: (self iconBlock: aNode).
		r color: aColor.
		r borderColor: self borderColor.
	].
	textModel announce: conf.```