{
	on: (ZnCharacterWriteStream on: Stdio stdout encoding: 'utf8').

	^ ZnCharacterReadStream
			on: self binaryReadStream
			encoding: anEncoding
	slots: { #stream . #cr . #lf . #previous . #lineEnding};
	package: 'Zinc-Character-Encoding-Core'
	^ self basicNew
			initialize;
			stream: aStream;
			yourself
		stream close
		^ stream flush

	| expectedString stream crStream |
	expectedString := 'a', OSPlatform current lineEnding, 'b'.
	{ String cr . String lf . String crlf } do: [ :lineEnd |
			stream := String new writeStream.
			crStream := ZnNewLineWriterStream on: stream.
			crStream
				<< 'a';
				<< lineEnd;
				<< 'b'.
			self assert: stream contents equals: expectedString ]
	"Write aCharacter to the receivers stream.
	Convert all line end combinations, i.e cr, lf, crlf, to the platform convention"

	(previous == cr and: [ aCharacter == lf ]) ifFalse: [
			(aCharacter == cr or: [ aCharacter == lf ]) 
				ifTrue: [ self newLine ]
				ifFalse: [ stream nextPut: aCharacter ] ].
	previous := aCharacter.